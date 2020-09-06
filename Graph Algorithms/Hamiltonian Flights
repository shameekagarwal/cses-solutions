#include<bits/stdc++.h>
using namespace std;
#define ll long long
#define MOD 1000000007
vector<int>adj[22];
ll dp[1100000][22];
int n;
ll F(int mask, int i)
{
    mask = mask ^ (1 << i);
    if (mask == 0 && i == n - 1)
        return 1;
    if (i == n - 1)
        return 0;
    if (dp[mask][i] != - 1)
        return dp[mask][i];
    dp[mask][i] = 0;
    for (auto j : adj[i])
    {
        if ((mask & (1 << j)))
            dp[mask][i] = (dp[mask][i] + F(mask, j)) % MOD;
    }
    return dp[mask][i];
}
int main()
{
    ios::sync_with_stdio(0);
    cin.tie(0); cout.tie(0);
    int m; cin >> n >> m;
    for (int i = 0; i < m; i++)
    {
        int a, b; cin >> a >> b; a--; b--;
        adj[a].push_back(b);
    }
    memset(dp, -1, sizeof(dp));
    cout << F((1 << n) - 1, 0);
    return 0;
}