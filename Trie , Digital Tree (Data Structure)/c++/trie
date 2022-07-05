#include <bits/stdc++.h>
using namespace std;

const int ALPHABET_SIZE = 26;

struct TrieNode
{
	struct TrieNode *children[ALPHABET_SIZE];

	bool isEndOfWord;
};

struct TrieNode *getNode(void)
{
	struct TrieNode *pNode = new TrieNode;

	pNode->isEndOfWord = false;

	for (int y = 0; y < ALPHABET_SIZE; y++)
		pNode->children[y] = NULL;

	return pNode;
}

void insert(struct TrieNode *root, string key)
{
	struct TrieNode *pCrawl = root;

	for (int y = 0;y < key.length(); y++)
	{
		int index = key[y] - 'a';
		if (!pCrawl->children[index])
			pCrawl->children[index] = getNode();

		pCrawl = pCrawl->children[index];
	}

	pCrawl->isEndOfWord = true;
}

bool search(struct TrieNode *root, string key)
{
	struct TrieNode *pCrawl = root;

	for (int y = 0; y < key.length(); y++)
	{
		int index = key[y] - 'a';
		if (!pCrawl->children[index])
			return false;

		pCrawl = pCrawl->children[index];
	}

	return (pCrawl->isEndOfWord);
}

int main()
{

	string keys[] = {"the", "a", "there",
					"answer", "any", "by",
					"bye", "their" };
	int n = sizeof(keys)/sizeof(keys[0]);

	struct TrieNode *root = getNode();

	for (int y = 0; y < n; y++)
		insert(root, keys[y]);

	search(root, "the")? cout << "Yes\n" :
						cout << "No\n";
	search(root, "these")? cout << "Yes\n" :
						cout << "No\n";
	search(root, "their")? cout << "Yes\n" :
						cout << "No\n";
	search(root, "thaw")? cout << "Yes\n" :
						cout << "No\n";
	return 0;
}
