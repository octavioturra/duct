# duct

A general purpose language

# example

```
sum = a b | a + b

mul = a b | a * b

sumul10 = { sum | mul 3 } 10

sumul10 10 

// 10 + 10 = 20
// 20 * 3 = 60

=======================================

sumActor = listen a b | a + b | print

actors = spawn 100 sumActor

send sumActor 20 30

nums = [1 2 3 4 5 6]

pairsMul10sum = [for c * 10 in nums where c % 2 is 0 into @ + c]

a = true
b = if a { 3 } | else { 10 }

sumul | strong | int 64 = a b c? d? |
      ref b strong |
      int 64 a b c |
      expectable a of int 64 |
      default c 10 of int 64 |
      when a | 
      match d  { 
          Ok d | a + b * c + d, 
          None | a + b + c
      } | precision 2 | [@ b]
      
sumul | after = log @

sumul | during = show Loader

sumul | after = hide Loader, clear sumul

arr | array 1000 | int 64 = [1 2 3 4 5]

=======================================

404 | after = renderError

getData = | fetch 'http://exampl.com' | when a status | render a

endpoint = listen { in | http | route "/users" } | query "..." | into Usuarios | json | http | out

=======================================
c = a |

d = c of Usuário | @nome + a

a = [tell c x *2 for x in { when fetch "google.com" | into UserIds } where x < 3]

=======================================
a = pop a b | sum a b | render

aa = spawn A 50

when aa | Some | print, None | panic

push aa 10 20
=======================================
a = unshift a b | sum a b | render

aa = spawn A 50

when aa | Some | print, None | panic

shift aa 10 20
=======================================
a = listen a b | sum a b | render

aa = spawn A 50

when aa | Some | print, None | panic

tell aa 10 20

=======================================

c = when a | 
        Some a | into Usuario,
        None | default Usuario
        
=======================================

a = atom 10
swap a 30
b = current a
c = previous a

```
