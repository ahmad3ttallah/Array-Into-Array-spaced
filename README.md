# Array-Into-Array-with-steps
Write a function that takes three arguments, 2 arrays (a and b) and 1 integer (c) then returns one array (d) which is created by inserting all elements in b into a at indexes which are spaced by the integer value.

    Consider all possible corner cases.
# e.g

    a = ["a", "b", "c", "d", "e", "f"]
    b = ["1", "2", "3"]
    c = 2

    d = ["a", "b", "1", "c", "d", "2", "e", "f", "3"]
    
    
----------------------------------------------------------------------------------------------------
    
    
# Solution

    import java.util.Arrays;

    /**
     * Write a function that takes three arguments, 2 arrays (a and b) and 1 integer (c)
     * then returns one array (d) which is created by inserting all elements in b into a
     * at indexes which are spaced by the integer value.
     * Consider all possible corner cases.
     * e.g
     * a = ["a", "b", "c", "d", "e", "f"]
     * b = ["1", "2", "3"]
     * c = 2
     * d = ["a", "b", "1", "c", "d", "2", "e", "f", "3"]
     * @author devah
     *
     */
    public class ArrayIntoArray {
        public static void main(String[] args) {
            String[] a = {"a", "b", "c", "d", "e", "f", "g", "h", "i"};
            String[] b = {"1", "2", "3", "4", "5", "6", "7"};
            int c = 3;
            String[] res = process(a, b, c);

            System.out.println(Arrays.toString(a));
            System.out.println(Arrays.toString(b));
            System.out.println(Arrays.toString(res));
        }

        public static String[] process(String[] a, String[] b, int c) {
            String[] res = new String[a.length + b.length];
            int aIdx = 0, bIdx = 0;
            for(int i = 0; i < res.length; i++) {
                if((i - c * (bIdx + 1) - bIdx) == 0 && bIdx < b.length) {
                    res[i] = b[bIdx];
                    bIdx++;
                } else if(aIdx < a.length) {
                    res[i] = a[aIdx];
                    aIdx++;
                } else if(bIdx < b.length){
                    res[i] = b[bIdx];
                    bIdx++;
                }
            }
            return res;
        }
    }
