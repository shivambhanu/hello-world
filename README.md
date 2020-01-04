#include<list>
#include<iostream>
using namespace std;

//CODE FOR JOSEPHUS PROBLEM.

int survivor(int n, int k)
{
	list<int> l = { 0,1,2,3,4,5,6 };
	auto it = l.begin();
	while (l.size() > 1)
	{
		for (int cnt = 1; cnt < k; cnt++)
		{
			it++;
			if (it == l.end())
			{
				it = l.begin();
			}
		}
		it = l.erase(it);
		if (it == l.end())
		{
			it = l.begin();
		}
	}
	return *l.begin();
}
int main()
{
	int n, k, res;
	//cout << "Total number of elements are: " << endl;
	//cin >> n;
	//cout << "Frequency is: " << endl;
	//cin >> k;

	res = survivor(7, 3);
	cout << "Survivor is: " << res;
	return 0;
}
