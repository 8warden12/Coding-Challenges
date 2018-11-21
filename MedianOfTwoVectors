#include <vector>
#include <stdio.h>
using namespace std;



double medianOfVectors(vector<int> &nums1, vector<int> &nums2)//INPUT: 2 sorted vectors OUTPUT: median of the 2 arrays
{
	vector<int> c(nums1.size() + nums2.size());//combined array
	
	auto aIter = nums1.begin();
	auto bIter = nums2.begin();
	
	if(nums1.empty())//if one array is empty, calculate and return the median of the other one
	{
		return (nums2.size()%2==0) ? (double)(nums2[nums2.size()/2] + nums2[(nums2.size()/2) - 1])/2.0 : (double)(nums2[nums2.size()/2]) ;	
	}else if(nums2.empty())
	{
		return (nums1.size()%2==0) ? (double)(nums1[nums1.size()/2] + nums1[(nums1.size()/2) - 1])/2.0 : (double)(nums1[nums1.size()/2]) ;	
	}
	
	
	
	for(vector<int>::iterator i = c.begin(); i != c.end(); ++i)
	{
		
		if(aIter == nums1.end())
		{
			copy(bIter, nums2.end(), i);
			break;
		}else if(bIter == nums2.end())
		{
			copy(aIter, nums1.end(), i);
			break;
		}
		
		
		//based off mergesort (merge step)
		if(*aIter < *bIter)//
		{
			if(aIter < nums1.end())
			{
				*(i) = *aIter;
			}else{
				*(i) = *bIter;
			}
			
			++aIter;
		}else{
			
			if(bIter < nums2.end())
			{
				*(i) = *bIter;
			}else{
				*(i) = *aIter;
			}
			
			++bIter;
		}
		
	}

	return (c.size()%2==0) ? (double)(c[c.size()/2] + c[(c.size()/2) - 1])/2.0 : (double)(c[c.size()/2]); //if combined array size is even, take average of middle 2 elements, if odd, return middle element	
	
}



int main()
{
	vector<int> a{1};
	vector<int> b{2,3,4,5,6,7,8,9,10};
	printf("%f",medianOfVectors(a,b));		
}
