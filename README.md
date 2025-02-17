package main

import (
	"fmt"
	"math"
)
const G = 6.67430e-11 //  (m^3 kg^-1 s^-2)

type Planet struct {
	Name     string
	Mass     float64 //  (kg)
	Distance float64 //  (m)
}

func gravitationalForce(m1, m2, r float64) float64 {
	return (G * m1 * m2) / (r * r)
}

func main() {
	planets := []Planet{
		{"Mercury", 3.3011e23, 5.791e10},
		{"Venus", 4.8675e24, 1.082e11},
		{"Earth", 5.972e24, 1.496e11},
		{"Mars", 6.4171e23, 2.279e11},
		{"Jupiter", 1.898e27, 7.785e11},
		{"Saturn", 5.683e26, 1.433e12},
		{"Uranus", 8.681e25, 2.877e12},
		{"Neptune", 1.024e26, 4.503e12},
	}

	fmt.Println("Gravitational Force between Planets in the Solar System (in Newtons):\n")

	for i := 0; i < len(planets); i++ {
		for j := i + 1; j < len(planets); j++ {
			force := gravitationalForce(planets[i].Mass, planets[j].Mass, math.Abs(planets[i].Distance-planets[j].Distance))
			fmt.Printf("Force between %s and %s: %.2e N\n", planets[i].Name, planets[j].Name, force)
		}
	}
}
