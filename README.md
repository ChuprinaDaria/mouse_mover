# mouse_mover
A lightweight Python script that simulates mouse movement to prevent your computer from going idle. Perfect for staying active online during meetings or avoiding system timeouts.




import pyautogui
import time

# Увімкнення функції Fail-Safe (увімкнено за замовчуванням)
pyautogui.FAILSAFE = True

print("Програма запущена.")
print("Перемістіть курсор у верхній лівий кут екрану (0, 0), щоб зупинити програму.")

try:
    while True:
        # Отримання поточного положення курсору
        x, y = pyautogui.position()

        # Переміщення курсору на нову позицію
        pyautogui.moveTo(x + 100, y + 100, duration=0.5)  # Рух на 100 пікселів вправо і вниз
        time.sleep(1)  # Затримка перед наступним рухом

        # Повернення курсору до початкової позиції
        pyautogui.moveTo(x, y, duration=0.5)
        time.sleep(1)
except pyautogui.FailSafeException:
    print("Програма зупинена через переміщення курсору у верхній лівий кут.")
except KeyboardInterrupt:
    print("Програма завершена вручну.")
