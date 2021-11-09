class Node {
    Node links[] = new Node[26]; 
    int cntEndWith = 0;
    int cntPrefix = 0;
    
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
    void increaseEnd() {
        cntEndWith++;  
    }
    void increasePrefix() {
        cntPrefix++; 
    }
    void deleteEnd() {
        cntEndWith--; 
    }
    void reducePrefix() {
        cntPrefix--; 
    }
    int getEnd() {
        return cntEndWith; 
    }
    int getPrefix() {
        return cntPrefix; 
    }
};
public class Trie {
    private Node root; 

    //Initialize your data structure here

    Trie() {
        root = new Node(); 
    }


    //Inserts a word into the trie

    public void insert(String word) {
        Node node = root;
        for(int i = 0;i<word.length();i++) {
            if(!node.containsKey(word.charAt(i))) {
                node.put(word.charAt(i), new Node()); 
            }
            node = node.get(word.charAt(i)); 
            node.increasePrefix(); 
        }
        node.increaseEnd(); 
    }


    public int countWordsEqualTo(String word) {
        Node node = root;
        for(int i = 0;i<word.length();i++) {
            if(node.containsKey(word.charAt(i))) {
                node = node.get(word.charAt(i));
            }
            else {
                return 0; 
            }  
        }
        return node.getEnd(); 
    }

    public int countWordsStartingWith(String word) {
        Node node = root;
        for(int i = 0;i<word.length();i++) {
            if(node.containsKey(word.charAt(i))) {
                node = node.get(word.charAt(i));
            }
            else {
                return 0; 
            }  
        }
        return node.getPrefix(); 
    }

    public void erase(String word) {
        Node node = root;
        for(int i = 0;i<word.length();i++) {
            if(node.containsKey(word.charAt(i))) {
                node = node.get(word.charAt(i));
                node.reducePrefix(); 
            }
            else {
                return;
            }
        }
        node.deleteEnd(); 
    }

}
