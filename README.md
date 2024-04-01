//二分答案法 1.例题力扣P875题 爱吃香蕉的珂珂
//          2.//力扣P410 分割数组的最大值
//          3. 牛客 机器人跳跃问题
//          4.力扣题P719  找出第K小的数对距离
//          5.力扣题P2141 同时运行n台电脑的最长运行时间
//          6.
//          7.
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
//第一题题解
/*
   bool check(vector<int>&piles,int h);
	int minEatingSpeed(vector<int>&piles, int h) {
		  int l=0;
		  int r=-1;
		  for(auto it:piles){
			if(it>r){
				r=it;
			}
		  }
		  while(l+1<r){
			int m=l+(r-l)/2;
			(check(piles,h,m)?r:l)=m;
		  }
		  return r;

	}
	bool check(vector<int>&piles,int h,int k){
		int sum=piles.size();
		  for(int p:piles){
			sum+=(p-1)/k;
			if(sum>h){
				return false;
			}
		  }
		  return true;
	}
*/
// 第二题题解
/*
	int splitArray(vector<int>& nums, int k) {
	long sum=0;
	for(int i=0;i<nums.size();i++){
		sum+=nums[i];
	}
	long ans=0;
	for(long l=0,r=sum,m,cur;l<=r;){
		m=l+(r-l)/2;
		cur=f(nums,m);
		if(cur<=k){
			ans=m;
			r=m-1;
		}
		else{
			l=m+1;
		}

	} return (int)ans;}

	int f(vector<int>&arr,long aim){
		int parts=1;
		int sum=0;
		for(int num:arr){
			if(num>aim){
				return  0x3f3f3f3f（表示int整型最大值）;
			}
			if(sum+num>aim){
				parts++;
				sum=num;
			}
			else{
				sum+=num;
			}
		}
		return parts;
	}
   
*/


/*第三题题解
//通关所需最小能量范围
int n; int sum = 0;const int N = 2e6 + 10;
int a[N]; //int a[N];
bool f(int energy,int max){
		for (int i = 1; i <= n; i++) {
			if (energy <=a[i]) {
				energy -= a[i] - energy;
			}
			else {
				energy +=  energy-a[i];
			}if (energy >= max) {
			return true;
		}
		if (energy < 0) {
			return false;
		  }
		}
		
		return true;


}
int two_part(int l, int r,int max) {
	int m, ans = -1; r = sum;
	while (l <= r) {
		m = l + (r - l) / 2;
		if (f(m, max)) {
			ans = m;
			r = m - 1;
		}
		else {
			l = m + 1;
		}
	}cout << ans << endl;
	return ans;

}
int mx;
void solve() {
	int l = 0, r =mx;
	two_part(l, r, mx);
}

int main() {
	cin >> n; mx = 0;
	for (int i = 1; i <= n; i++) {
		cin >> a[i]; sum += a[i];
		if (a[i] > mx) {
			mx = a[i];
		}

	}
	int t = 1;
	while (t--) {
		solve();
	}

}
*/
//第四题题解
/*int smallestDistancePair(vector<int>& nums, int k) {
	int n = nums.size();
	sort(nums.begin(), nums.end());
	int ans = 0;
	for (int l = 0, r = nums[n - 1] - nums[0], m, cnt; l <= r;) {
		m = l + (r - l) / 2;
		cnt = f(nums, m);
		if (cnt >= k) {
			r = m - 1;
			ans = m;
		}
		else {
			l = m + 1;
		}
	}

	return ans;
}
int f(vector<int>& arr, int limit) {
	int cnt = 0;
	for (int l = 0, r = 0; l < arr.size(); l++) {
		while (r + 1 < arr.size() && arr[r + 1] <= arr[l] + limit) {
			r++;满足r+1不越界以及r+1与l所对于数值不超过limit
		}
		cnt += r - l;3 4 5 10 17 21 判断 l-r区间能取得多少分满足限制的数对
	}return cnt;
}
*/
//第五题题解
/*
long long maxRunTime(int n, vector<int>& batteries) {
	long max = -1; long sum = 0;
	for (int i : batteries) {
		if (i > max) {
			max = i;
		}
		sum += i;
	}
	long ans = 0;
	if (sum >= max * n) {
		return sum / n;
	}
	//sort(batteries.begin(),batteries.end());
	for (long l = 0, r = max, m; l <= r;) {
		m = l + (r - l) / 2;
		if (f(batteries, n, m)) {
			ans = m;
			l = m + 1;
		}
		else {
			r = m - 1;
		}
	}
	return ans;

}

bool f(vector<int>& arr, int num, long time) {
	long sum = 0;
	for (int x : arr) {
		if (x > time) {
			num--;
		}
		else {
			sum += x;
		}if (sum >= (long)num * time) {
			return true;
		}
	}

	return false;
}
*/




