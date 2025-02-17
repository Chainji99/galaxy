#include <stdio.h>
#include <math.h>

#define G 6.67430e-11  (m^3 kg^-1 s^-2)

typedef struct {
    char name[20];
    double mass;  
    double distance; 
} Planet;
double gravitational_force(double m1, double m2, double r) {
    return (G * m1 * m2) / (r * r);
}

int main() {
    Planet planets[] = {
        {"Mercury", 3.3011e23, 5.791e10},
        {"Venus", 4.8675e24, 1.082e11},
        {"Earth", 5.972e24, 1.496e11},
        {"Mars", 6.4171e23, 2.279e11},
        {"Jupiter", 1.898e27, 7.785e11},
        {"Saturn", 5.683e26, 1.433e12},
        {"Uranus", 8.681e25, 2.877e12},
        {"Neptune", 1.024e26, 4.503e12}
    };
    int num_planets = sizeof(planets) / sizeof(planets[0]);
    int i, j;   
    printf("Gravitational Force between Planets in the Solar System (in Newtons):\n\n");
    for (i = 0; i < num_planets; i++) {
        for (j = i + 1; j < num_planets; j++) {
            double force = gravitational_force(planets[i].mass, planets[j].mass, fabs(planets[i].distance - planets[j].distance));
            printf("Force between %s and %s: %.2e N\n", planets[i].name, planets[j].name, force);
        }
    }
    return 0;
}
