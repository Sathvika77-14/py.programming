class Solution(object):
    def fullJustify(self, words, maxWidth):
        """
        :type words: List[str]
        :type maxWidth: int
        :rtype: List[str]
        """
        #coun the characters in words, e.g.
        #"This", "is", "an", "example", "of", "text", "justification."
        #sums=[0, 4, 6, 8, 15, 17, 21, 35]
        count=0
        sums=[0]
        paragraph=[]
        for w in words:
            count+=len(w)
            sums.append(count)
        
        pos1=0   #start with pos1
        pos2=1

        #find pos2 that create the line
        while pos1<len(words):
            while pos2<len(words) and (sums[pos2]-sums[pos1]+pos2-pos1+len(words[pos2]))<=maxWidth:
                pos2+=1

            numWords=pos2-pos1
            #calculate the spaces total to be distributed between the word
            spacesTotal=maxWidth-sums[pos2]+sums[pos1]

            #create an array of number of "spaces"
            if (numWords<=1):  #if only one word
                spaces=[spacesTotal]
            else:
                if pos2==len(words): #last line
                    spaces=[1]*numWords                 #the words separated by one space
                    spaces[-1]=spacesTotal-numWords+1   #the last word add the rest of spaces
                else:
                    minSpace=(spacesTotal)//(numWords-1)
                    spaces=[minSpace]*numWords          #all the words separated by the same space
                    spaces[-1]=0                        #but the last no

                    #distibute rest of spaces to fullfilled the maxLengt
                    restSpaces=(spacesTotal-minSpace*(numWords-1))
                    while restSpaces:
                        for i in range(numWords):
                            spaces[i]+=1
                            restSpaces-=1
                            if not restSpaces:
                                break
            #a line will be the words+spaces
            paragraph.append(''.join([(words[pos1+i]+(' '*spaces[i])) for i in range(numWords)]))
            pos1=pos2
            pos2=pos1+1
        return paragraph

#only to show the paragraphs in a "beauty way"
def printParagraph(paragraph):
    for p in paragraph:
        print('['+p+']')

sol=Solution()
printParagraph(sol.fullJustify(words = ["This", "is", "an", "example", "of", "text", "justification."], maxWidth = 16))

        
        
