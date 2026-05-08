
Today I learned about Modular Arithmetic.

First I solved the challenged on Cryptohack.
Later I found that there was a great website about [Modular Arithmetic](https://www.ctfrecipes.com/cryptography/general-knowledge/maths/modular-arithmetic/greatest-common-divisor)

### Challenges

1. Greatest Common Divisor
		This was fairly easy to solve as I knew the algorithm.

2. Extended GCD
		This was also easy although I had to revise the algorithm. Writing python code was easy.

3. Modular Arithmetic 1
		You just have to find the remainder and submit smallest among two.

4. Modular Arithmetic 2
		This is easy if you know [Fermat's little theorem](https://www.ctfrecipes.com/cryptography/general-knowledge/maths/modular-arithmetic/fermats-little-theorem). Which is in the form $a^{p-1} \equiv 1 (mod p)$. So the answer is 1.

5. Modular Inverting
		It's also related to little theorem. And can be calculated using extended euclidean algorithm.
		Python has function `egcd()` which returns `gcd, u, v` and you have to simply perform `u % p`.
		There is another method also:
			By extending fermat's little theorem equation we get:
				$a^{p-2}$ % p = $a^{-1}$
		 So, we can calculate by `pow(a, p - 2, p)`.

6. Quadratic Residues
		This was a new concept to me. So I had to learn this for a bit. More on this on above website.

7. Legendre Symbol
		This was quite easy to understand once you understand Quadratic Residue. 
		But I had problem while solving this challenge. There was a hint but I had no clue. So I decided to look for solution. Then I found [this](https://crypto.stackexchange.com/questions/20993/significance-of-3mod4-in-squares-and-square-roots-mod-n/20994#20994). 
		After reading this, I solve the challenge.

8. Modular Square Root
		This was a quite challenging. At first, I couldn't solve at all. Then I learned there's an algorithm called [Tornelli Shanks Algorithm](Topics/Tornelli Shanks Algorithm). You just have to implement the algorithm and it will be solved.

9. Chinese Remainder Theorem
		This was easy for me as I learned it in the college in discrete math. I just had to implement the algorithm.

10. Adrien's Signs
		I tried to solve this but couldn't solve this.
		Complete explanation is [here](Topics/Adrien_signs_solution).
				
11. Modular Binomials
		This was interesting and fun. I just need to simplify the equation.
		It uses [Binomial Expansion](https://en.wikipedia.org/wiki/Binomial_theorem). I also tried to simply equation by hand and I was on point.
		After simplify q comes down to this: 
		q = `gcd(pow(a2,(-e2 * e1),N) * pow(c2, e1, N) - pow(a1, (-e1 * e2), N) * pow(c1, e2, N), N)`

---

And that was it. It was really fun and full of learnings.
I enjoyed a lot and learned a lot. Hope to learn tomorrow.