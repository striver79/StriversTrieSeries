
import java.util.ArrayList;
class Node {
    Node links[] = new Node[26]; 
    boolean flag = false; 
    
    public Node() {
        
    }
    
    boolean containsKey(char ch) {
        return (links[ch - 'a'] != null); 
    }
    Node get(char ch) {
        return links[ch-'a']; 
    }
    void put(char ch, Node node) {
        links[ch-'a'] = node; 
    }
    void setEnd() {
        flag = true; 
    }
    boolean isEnd() {
        return flag; 
    }
};

public class Solution 
{
	public static int countDistinctSubstrings(String s) 
	{
		Node root = new Node(); 
        int n = s.length(); 
        int cnt = 0; 
        for(int i = 0; i < n;i++) {
            Node node = root; 
            for(int j = i;j<n;j++) {
                if(!node.containsKey(s.charAt(j))) {
                    node.put(s.charAt(j), new Node()); 
                    cnt++; 
                }
                node = node.get(s.charAt(j));  
            }
        }
        return cnt + 1; 
	}
}
