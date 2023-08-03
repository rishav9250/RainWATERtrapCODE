# RainWATERtrapCODE
import java.util.*;
public class ARRAYtrappedwater {
    public static int TRAPEDWATER(int height[]){
        int n =height.length;
        int LeftMAX[] = new int[n];
        LeftMAX[0] =height[0];
        for(int i=1;i<n;i++){
            LeftMAX[i] =Math.max(height[i],LeftMAX[i-1]);
        }
        int RightMax[] = new int[n];
        RightMax[n-1] =height[n-1];
        for(int i=n-2;i>=0;i--){
            RightMax[i] =Math.max(height[i], RightMax[i+1]);
        }
int trappedwater=0;
for(int i=0;i<n;i++){
    int waterLevel = Math.min(LeftMAX[i],RightMax[i]);
    trappedwater +=waterLevel - height[i];
}
return trappedwater;
} 
public static void main(String[] args) {
    int height[] = {4, 2, 0, 6, 3, 2, 5};
   System.out.println(TRAPEDWATER(height));
}
}





