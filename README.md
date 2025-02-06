### LLM Fortran bugs
Examples of invalid Fortran code by LLMs

from ChatGPT o3-mini-high on 2025-02-06:
```fortran
module m
implicit none
contains
subroutine foo(tf)
logical, intent(in), optional :: tf
! line below not valid -- gives run-time error with gfortran
if (present(tf) .and. tf) print*,"true"
end subroutine foo
end module m

program main
use m, only: foo
implicit none
call foo()
end program main
```
