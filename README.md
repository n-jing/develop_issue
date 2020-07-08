# develop_issue
issues in development

## compile error when SimplicialLDLT and SimplicialLLT solve RowMajor SparseMatrix with eigen3.3.7. However, SimplicialLDLT works on ColMajor SparseMatrix well.
```cpp
#include<Eigen/SparseCholesky>

int main(int argc, char ** argv)
{
  Eigen::SparseMatrix<double, Eigen::RowMajor> A;
  Eigen::SimplicialLDLT<Eigen::SparseMatrix<double, Eigen::RowMajor>> solver;
  solver.compute(A);

  Eigen::Matrix<double, -1, 1> b;
  Eigen::Matrix<double, -1, 1> x;
  x = solver.solve(b);

  return 0;
}
```
## numeric method
1. cg method [cg](https://zhuanlan.zhihu.com/p/98642663)