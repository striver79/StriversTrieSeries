#include<bits/stdc++.h>
struct Node {
    Node *links[2]; 
 
    bool containsKey(int ind) {
        return (links[ind] != NULL); 
    }
    Node* get(int ind) {
        return links[ind]; 
    }
    void put(int ind, Node* node) {
        links[ind] = node; 
    }
}; 
class Trie {
    private: Node* root; 
public:
    Trie() {
        root = new Node(); 
    }
    
    public: 
    void insert(int num) {
        Node* node = root;
        // cout << num << endl; 
        for(int i = 31;i>=0;i--) {
            int bit = (num >> i) & 1; 
            if(!node->containsKey(bit)) {
                node->put(bit, new Node()); 
            }
            node = node->get(bit); 
        }
    }
    public:
    int findMax(int num) {
        Node* node = root; 
        int maxNum = 0; 
        for(int i = 31;i>=0;i--) {
            int bit = (num >> i) & 1; 
            if(node->containsKey(!bit)) {
                maxNum = maxNum | (1<<i); 
                node = node->get(!bit); 
            }
            else {
                node = node->get(bit); 
            }
        }
        return maxNum; 
    }
};
vector<int> maxXorQueries(vector<int> &arr, vector<vector<int>> &queries){
	vector<int> ans(queries.size(), 0); 
    vector<pair<int, pair<int,int>>> offlineQueries; 
    sort(arr.begin(), arr.end()); 
    int index = 0;
    for(auto &it: queries) {
        offlineQueries.push_back({it[1],{it[0], index++}}); 
    }
    sort(offlineQueries.begin(), offlineQueries.end()); 
    int i = 0; 
    int n = arr.size(); 
    Trie trie; 
    
    for(auto &it : offlineQueries) {
        while(i < n && arr[i] <= it.first) {
            trie.insert(arr[i]); 
            i++; 
        }
        if(i!=0) ans[it.second.second] = trie.findMax(it.second.first); 
        else ans[it.second.second] = -1; 
    }
    return ans; 
}
