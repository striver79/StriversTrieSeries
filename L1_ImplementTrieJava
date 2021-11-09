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
public class Trie {
    private static Node root; 

    //Initialize your data structure here

    Trie() {
        root = new Node(); 
    }


    //Inserts a word into the trie

    public static void insert(String word) {
        Node node = root;
        for(int i = 0;i<word.length();i++) {
            if(!node.containsKey(word.charAt(i))) {
                node.put(word.charAt(i), new Node()); 
            }
            node = node.get(word.charAt(i)); 
        }
        node.setEnd(); 
    }


    //Returns if the word is in the trie

    public static boolean search(String word) {
        Node node = root; 
        for(int i = 0;i<word.length();i++) {
            if(!node.containsKey(word.charAt(i))) {
                return false; 
            }
            node = node.get(word.charAt(i)); 
        }
        if(node.isEnd()) {
            return true; 
        }
        return false; 
    }

    
    //Returns if there is any word in the trie that starts with the given prefix

    public static boolean startsWith(String prefix) {
        Node node = root; 
        for(int i = 0;i<prefix.length();i++) {
            if(!node.containsKey(prefix.charAt(i))) {
                return false; 
            }
            node = node.get(prefix.charAt(i)); 
        }
        return true; 
    }
}
