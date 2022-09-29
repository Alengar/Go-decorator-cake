package main

import "fmt"

func main() {

	theFrenchCake := &yogurtTopping{
		cake: &fruitTopping{
			cake: &hazelnutTopping{
				cake: newSpongeCake(),
			},
		},
	}

	chocolateTruffleCake := &chocolateTopping{
		cake: newSpongeCake(),
	}

	fmt.Printf("Price of theFrenchCake is $%.2f with %d calories.\n",
		theFrenchCake.getPrice(),
		theFrenchCake.getCalories())
	fmt.Printf("Price of chocolateTruffleCake is $%.2f with %d calories.\n",
		chocolateTruffleCake.getPrice(),
		chocolateTruffleCake.getCalories())
}

type cake interface {
	getPrice() float64
	getCalories() int
}

type spongeCake struct { // корж для торта, то есть его основание
	calories int
	price    float64
}

func newSpongeCake() *spongeCake {
	return &spongeCake{
		calories: 280,
		price:    5.00,
	}
}

func (c *spongeCake) getPrice() float64 {
	return c.price
}

func (c *spongeCake) getCalories() int {
	return c.calories
}

const (
	chocolatePrice = 2.35
	fruitPrice     = 3.00
	yogurtPrice    = 2.50
	hazelnutPrice  = 2.25

	chocolateCalories = 250
	fruitCalories     = 150
	yogurtCalories    = 200
	hazelnutCalories  = 150
)

type chocolateTopping struct {
	cake cake
}
type fruitTopping struct {
	cake cake
}
type yogurtTopping struct {
	cake cake
}
type hazelnutTopping struct {
	cake cake
}

func (p *chocolateTopping) getPrice() float64 {
	return p.cake.getPrice() + chocolatePrice
}
func (a *fruitTopping) getPrice() float64 {
	return a.cake.getPrice() + fruitPrice
}
func (a *yogurtTopping) getPrice() float64 {
	return a.cake.getPrice() + yogurtPrice
}
func (t *hazelnutTopping) getPrice() float64 {
	return t.cake.getPrice() + hazelnutPrice
}

func (p *chocolateTopping) getCalories() int {
	return p.cake.getCalories() + chocolateCalories
}
func (a *fruitTopping) getCalories() int {
	return a.cake.getCalories() + fruitCalories
}
func (a *yogurtTopping) getCalories() int {
	return a.cake.getCalories() + yogurtCalories
}
func (t *hazelnutTopping) getCalories() int {
	return t.cake.getCalories() + hazelnutCalories
}
