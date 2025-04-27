class Solution(object):
    def insert(self, intervals, newInterval):
        import bisect
        t = bisect.bisect(intervals, newInterval)
        if t>0 and intervals[t-1][1]>= newInterval[0]:
            intervals[t-1][1] = max(intervals[t-1][1], newInterval[1])
        else:
            bisect.insort(intervals, newInterval)
            t+=1
        while t<len(intervals) and intervals[t][0]<= intervals[t-1][1]:
            intervals[t][0]=intervals[t-1][0]
            intervals[t][1] = max(intervals[t-1][1], intervals[t][1])
            intervals[t-1]= None
            t+=1
        return [i for i in intervals if i]
