import java.util.*;
interface Sorter<T extends Comparable<T>> {
    void sort(List<T> list);
}
public class Main<T extends Comparable<T>> implements Sorter<T> {
    public void sort(List<T> list) {
        for (int j = 0; j < list.size() - 1; j++)
            for (int a = 0; a < list.size() - j - 1; a++) {
                if (list.get(a).compareTo(list.get(a + 1)) > 0) {
                } else {
                    T temp = list.get(a + 1);
                    list.set(a + 1, list.get(a));
                    list.set(a, temp);
                }
            }
    }
    public static void main(String[] args) {
        List<Integer> ar = new ArrayList<Integer>() {
            {
                add(2);
                add(3);
                add(5);
                add(8);
                add(2);
            }
        };
        Main s = new Main();
        s.sort(ar);
        for (int i = 0; i < ar.size(); i++) {
            System.out.print(ar.get(i).toString() + " ");
        }

    }

}
