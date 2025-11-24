# Social-Networks-and-Recomendation-Systems

Short project description
- Analyses of social and infrastructure networks, empirical degree distributions, survival/CCDF estimation (including Kaplan–Meier), assortativity, path lengths, and simple recommendation-system experiments. Notebooks in `Labs/` contain step-by-step exercises and visualizations.


How to run
1. Create and activate a virtual environment (Windows):
   - python -m venv venv
   - venv\Scripts\activate
2. Install dependencies:
   - pip install jupyterlab numpy scipy pandas networkx matplotlib seaborn
3. Start Jupyter:
   - jupyter lab
4. Open the notebooks in `Labs/` and run cells.

Notes and common pitfalls
- Edge lists:
  - If an `.edges` file has a weight column (single float per edge), use read_edgelist with `data=(("weight", float),)`:
    ```python
    G = nx.read_edgelist("path/to/file.edges", create_using=nx.Graph(), nodetype=int, data=(("weight", float),))
    ```
  - If edge files have other formats, inspect the first lines to choose `delimiter`, `comments`, and `data` arguments.
- Matrix Market (.mtx):
  - Read with SciPy and convert to NetworkX:
    ```python
    from scipy.io import mmread
    import networkx as nx
    M = mmread("power-1138-bus.mtx")
    G = nx.from_scipy_sparse_matrix(M)
    ```


