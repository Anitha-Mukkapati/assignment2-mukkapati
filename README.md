# assignment2-mukkapati

# Anitha Mukkapati

###### My Favorite place in the world is Maldives

>The Maldives, a collection of more than a thousand islands in the **Indian Ocean**, is known for its clear emerald waters, beautiful beaches that stretch as far as the eye can see, and of course **luxurious overwater bungalows**. With features like these, the archipelago makes for an idyllic sanctuary where guests can **snorkel**, **scuba dive**, **swim**, and **savor** some truly unforgettable sunsets. Aside from being one of the most **stunning island getaways in the world**, the Maldives is also a perfect addition to an itinerary for travelers visiting magnificent South Asian cities or Middle Eastern capitals.
***
# Heading for access to reach order list and unorder list
1. Maryville 
2. New York City
   1. Statue of Liberty
   2. Terminal
3. utah
* Road trips
* Backpacking
  * Cycling
  * Fishing
  * campaigning

  **[LinktoAboutme.md](AboutMe.md)**

  # Heading about creating a table food/drinks

  Introduction:
   The following is to create a table with at least 4food/drinksthat you would recommend someone try.Include a short paragraph that introduces the table.

|Mandatory  |fav1       |fav2      |fav3         |fav4      |
|:-------:  | :-------: | :-------:| :--------:  | :-------:|
|food       |chicken    |Idly      |panipuri     |Drink     |
|location   |guntur     |Vijaywada |hyderbad     |Thumps    |
|Type       |Spicy      | with Ghee|1 plate      |Large     |
|Amout      |50-40      |40-30     |30-20        |20-10     | 

---
# quotes section
>"Life is like riding a bicycle. To keep your balance you must keep moving."
>Author:*Albert Einstein* <br>
> "No problem can be solved from the same level of consciousness that created it."
> Author:*Albert Einstein*

----
# create a new section about code Fencing 
Dynamic programming is both a mathematical optimization method and a computer programming method. The method was developed by Richard Bellman in the 1950s and has found applications in numerous fields, from aerospace engineering to economics.quick-link to the source code <https://en.wikipedia.org/wiki/Dynamic_programming>
```
int zero_matrix(vector<vector<int>> a) {
    int n = a.size();
    int m = a[0].size();

    int ans = 0;
    vector<int> d(m, -1), d1(m), d2(m);
    stack<int> st;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < m; ++j) {
            if (a[i][j] == 1)
                d[j] = i;
        }

        for (int j = 0; j < m; ++j) {
            while (!st.empty() && d[st.top()] <= d[j])
                st.pop();
            d1[j] = st.empty() ? -1 : st.top();
            st.push(j);
        }
        while (!st.empty())
            st.pop();

        for (int j = m - 1; j >= 0; --j) {
            while (!st.empty() && d[st.top()] <= d[j])
                st.pop();
            d2[j] = st.empty() ? m : st.top();
            st.push(j);
        }
        while (!st.empty())
            st.pop();

        for (int j = 0; j < m; ++j)
            ans = max(ans, (i - d[j]) * (d2[j] - d1[j] - 1));
    }
    return ans;
}

```
quick-link to the source code <https://cp-algorithms.com/dynamic_programming/zero_matrix.html>
