# polymorphism-assignment 
class Superhero:
    def __init__(self, name, secret_identity, powers, origin_story):
        self.name = name
        self.secret_identity = secret_identity
        self.powers = powers
        self.origin_story = origin_story
        self.energy_level = 100
        
    def use_power(self, power_index):
        if power_index < len(self.powers):
            power = self.powers[power_index]
            print(f"{self.name} uses {power}!")
            self.energy_level -= 10
        else:
            print("Power not available!")
    
    def rest(self):
        print(f"{self.name} is resting to regain energy.")
        self.energy_level = min(100, self.energy_level + 30)
        
    def describe(self):
        print(f"Superhero: {self.name}")
        print(f"Secret Identity: {self.secret_identity}")
        print("Powers:", ", ".join(self.powers))
        print(f"Energy Level: {self.energy_level}%")
        
    def save_civilian(self):
        print(f"{self.name} saves a civilian in distress!")
        self.energy_level -= 5


# Inheritance example - A specific type of superhero
class MutantSuperhero(Superhero):
    def __init__(self, name, secret_identity, powers, origin_story, mutation_level):
        super().__init__(name, secret_identity, powers, origin_story)
        self.mutation_level = mutation_level
        
    def mutate(self):
        print(f"{self.name}'s mutation level increases!")
        self.mutation_level += 1
        self.energy_level = 100  # Mutation refreshes energy
        
    def describe(self):  
        super().describe()
        print(f"Mutation Level: {self.mutation_level}")


# Create instances
spark = Superhero("Captain Spark", "John Watts", 
                 ["Electric Blast", "Lightning Speed", "EMP Wave"],
                 "Struck by experimental energy beam during a storm")

wolverine = MutantSuperhero("Wolverine", "Logan", 
                          ["Healing Factor", "Adamantium Claws", "Enhanced Senses"],
                          "Weapon X experiment", 10)

# Test the methods
spark.describe()
spark.use_power(0)
spark.save_civilian()

print("\n")

wolverine.describe()
wolverine.mutate()
wolverine.use_power(1)(Class superhero)
2(ANIMAL MOVEMENT)class Animal:
    def __init__(self, name):
        self.name = name
        
    def move(self):
        pass  # To be overridden by subclasses
        
    def speak(self):
        print(f"{self.name} makes a sound.")

class Bird(Animal):
    def move(self):
        print(f"{self.name} is flying! 🕊️")
        
    def speak(self):
        print(f"{self.name} says: Tweet tweet! �")

class Fish(Animal):
    def move(self):
        print(f"{self.name} is swimming! 🐠")
        
    def speak(self):
        print(f"{self.name} says: Blub blub! 💦")

class Snake(Animal):
    def move(self):
        print(f"{self.name} is slithering! 🐍")
        
    def speak(self):
        print(f"{self.name} says: Hiss hiss! ⚡")

class Kangaroo(Animal):
    def move(self):
        print(f"{self.name} is hopping! 🦘")
        
    def speak(self):
        print(f"{self.name} says: Chortle chortle! 🎶")


# Create a list of animals
animals = [
    Bird("Robin"),
    Fish("Nemo"),
    Snake("Viper"),
    Kangaroo("Joey")
]

# Demonstrate polymorphism
for animal in animals:
    animal.move()
    animal.speak()
    print()  # Blank line for separation


