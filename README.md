
#include<bits/stdc++.h>
using ll=long long;
using namespace std;
int main(){
     ll n;cin>>n;
     vector<int>v(n),v1(n);
     for(auto &i:v)cin>>i;
     v1=v;
     sort(v1.begin(),v1.end());
     vector<ll>suff(n,0);
     suff[n-1]=v1[n-1];
     for(int i =n-2;i>=0;i--){
          suff[i]=suff[i+1]+v1[i];
     }
     for(int i=0;i<n;i++){
         ll l=0;
         ll r=v1.size()-1;
         ll ans=-1;
        while(l<=r){
        ll mid=(l+r)/2;
         if(v1[mid]>v[i]){
           ans=mid;
           r=mid-1;
         }else l=mid+1;
       }

       if(ans==-1)cout<<0<<" ";
       else cout<<suff[ans]<<" ";

     }cout<<endl;

     //O(nlog(n))



  return  0;
}
