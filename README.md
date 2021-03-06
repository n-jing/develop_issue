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
2. newton method [newton](https://pjskd1.github.io/2019/03/07/%E7%89%9B%E9%A1%BF%E6%B3%95%E4%B8%8E%E6%8B%9F%E7%89%9B%E9%A1%BF%E6%B3%95/) and [newton](https://zhuanlan.zhihu.com/p/29672873)
3. implicit and explicit euler [explicit euler](https://jinyu.li/2017/05/03/pde-basics-1/), [semi-implicit euler](https://jinyu.li/2017/05/09/pde-basics-2/). [implicit euler](https://jinyu.li/2017/05/11/pde-basics-3/). [energy conservation](https://adamwermus.wordpress.com/2016/12/05/comparing-conservation-of-energy-to-the-simple-pendulum-model/)