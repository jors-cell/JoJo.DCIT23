#act1 ni Ancajas
import math

def compute_surface_area(R, r):
    # surface area formula: (2πR) × (2πr)
    return (2 * 3.1416 * R) * (2 * 3.1416 * r)

def compute_volume(R, r):
    # volume formula: (2πR) × (πr2)
    return (2 * 3.1416 * R) * (3.1416 * r**2)

def get_input():
    while True:
        try:
            R = float(input("Enter the major radius : "))
            r = float(input("Enter the minor radius : "))
            if R <= 0 or r <= 0:
                print("Neither radius can be zero or negative. Please try again.")
            elif r > R:
                print("Minor radius cannot be greater than the major radius. Please try again.")
            else:
                return R, r
        except ValueError:
            print("Invalid input. Please try again.")

def main():
    while True:
        print("Chose between 1/2 to compute:")
        print("1. Surface Area of the Torus")
        print("2. Volume of the Torus")
        print("3. Exit")
        
        choice = input("Enter your choice (1/2/3): ")
        
        if choice == '1':
            R, r = get_input()
            surface_area = compute_surface_area(R, r)
            print(f"The Surface Area of the Torus is: {surface_area:.2f}")
        elif choice == '2':
            R, r = get_input()
            volume = compute_volume(R, r)
            print(f"The Volume of the Torus is: {volume:.2f}")
        elif choice == '3':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please select 1, 2, or 3.")
        
        # if to continue or exit
        continue_choice = input("Do you want to compute another set of values? (yes/no): ").strip().lower()
        if continue_choice != 'yes':
            print("Exiting...")
            break
if __name__ == "__main__":
    main()

