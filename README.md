# 6days30company_challange

## circle-and-rectangle-overlapping
bool checkOverlap(int r, int xC, int yC, int x1, int y1, int x2, int y2) {
        int close_x=0,close_y=0;
        if(xC<x1)close_x=x1-xC;
        if(xC>x2)close_x=xC-x2;

        if(yC<y1) close_y=y1-yC;
        if(yC>y2) close_y=yC-y2;

        if((close_x*close_x)+(close_y*close_y)<=r*r) return true;
        return false;

    }
