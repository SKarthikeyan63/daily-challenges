class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> pascal = new ArrayList();
        for (int i = 0; i < numRows; i++) {
            List<Integer> row = new ArrayList();
            for (int j = 0; j <= i; j++) {
                if (j == 0 || j == i) {
                    row.add(1);
                } else {
                    List<Integer> previousRow = pascal.get(i - 1);
                    row.add(previousRow.get(j) + previousRow.get(j - 1));
                }
            }
            pascal.add(row);
        }
        return pascal;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        List<List<Integer>> result = solution.generate(5);
        for (List<Integer> row : result) {
            System.out.println(row);
        }
    }
}
