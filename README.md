# 6days30company_challange

## 1.circle-and-rectangle-overlapping
bool checkOverlap(int r, int xC, int yC, int x1, int y1, int x2, int y2) {

        int close_x=0,close_y=0;
        if(xC<x1)close_x=x1-xC;
        if(xC>x2)close_x=xC-x2;

        if(yC<y1) close_y=y1-yC;
        if(yC>y2) close_y=yC-y2;

        if((close_x*close_x)+(close_y*close_y)<=r*r) return true;
        return false;

    }

 ##3. Russian doll envelopes
 
 class Solution {
public:

    static bool comp(vector<int>&a,vector<int>&b){
        if(a[0]==b[0]){
            return a[1]>b[1];
        }else{
            return a[0]<b[0];
                    }
    }
    int maxEnvelopes(vector<vector<int>>& envelopes) {
        sort(envelopes.begin(),envelopes.end(),comp);
        int n=envelopes.size();
        vector<int>temp;
        temp.push_back(envelopes[0][1]);
        for(int i=1;i<n;i++){
            if(temp.back()<envelopes[i][1]){
                temp.push_back(envelopes[i][1]);
            }else{
                auto ind=lower_bound(temp.begin(),temp.end(),envelopes[i][1])-temp.begin();
                temp[ind]=envelopes[i][1];
            }
        }
        return temp.size();
        
    }
};
