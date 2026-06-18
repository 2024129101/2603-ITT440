# 2603-ITT440
## Sequential vs Parallel example
**Sequential Execution**
The program executes the classes strictly one after another Square --> Cube --> Fourth.
The terminal output is clean, ordered, and perfectly predictable. It uses minimal system resources.
It takes longer to complete because the next class must wait for the previous one to finish all 10,000, 000 loops.
```
import math


# --- Fungsi Pembantu untuk Semak Nombor Perdana ---
def is_prime(n):
    if n <= 1:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False  # Elakkan nombor genap lain

    # Semak pembahagi ganjil sehingga punca kuasa dua n
    for i in range(3, int(math.sqrt(n)) + 1, 2):
        if n % i == 0:
            return False
    return True


# --- Class-Class Utama ---
class SquarePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        print("--- Memulakan Kuasa Dua Nombor Perdana ---")
        for x in range(self.limit):
            if is_prime(x):
                print(f"Square Prime: {x}^2 = {x**2}")


class CubePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        print("\n--- Memulakan Kuasa Tiga Nombor Perdana ---")
        for x in range(self.limit):
            if is_prime(x):
                print(f"Cube Prime:   {x}^3 = {x**3}")


class FourthPowerPrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        print("\n--- Memulakan Kuasa Empat Nombor Perdana ---")
        for x in range(self.limit):
            if is_prime(x):
                print(f"Fourth Prime: {x}^4 = {x**4}")


# --- Sequential Execution ---
if __name__ == "__main__":
    # Cetus objek
    squarer = SquarePrinter()
    cuber = CubePrinter()
    fourther = FourthPowerPrinter()

    print("Memulakan pengiraan secara sequential (berperingkat)...\n")

    # Jalankan satu persatu mengikut turutan
    squarer.run()  # Selesai ini baru masuk baris bawah
    cuber.run()  # Selesai ini baru masuk baris bawah
    fourther.run()

    print("\nSemua pengiraan selesai mengikut urutan!")
```

***Multiprocessing - Multi-threading***
It runs all three classes within the same process using multiple threads.
```
import threading
import math


# --- Fungsi Pembantu untuk Semak Nombor Perdana ---
def is_prime(n):
    if n <= 1:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False

    for i in range(3, int(math.sqrt(n)) + 1, 2):
        if n % i == 0:
            return False
    return True


# --- Class-Class Utama ---
class SquarePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        for x in range(self.limit):
            if is_prime(x):
                # Ditambah label [Thread-1] untuk mudahkan anda nampak perbezaan di terminal
                print(f"[Thread-1] Square Prime: {x}^2 = {x**2}")


class CubePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"[Thread-2] Cube Prime:   {x}^3 = {x**3}")


class FourthPowerPrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"[Thread-3] Fourth Prime: {x}^4 = {x**4}")


# --- Multi-threading Execution ---
if __name__ == "__main__":
    # Cetus objek
    squarer = SquarePrinter()
    cuber = CubePrinter()
    fourther = FourthPowerPrinter()

    print(
        "Memulakan pengiraan nombor perdana menggunakan Multi-threading...\n"
    )

    # Cipta 3 thread berbeza untuk setiap class
    thread1 = threading.Thread(target=squarer.run)
    thread2 = threading.Thread(target=cuber.run)
    thread3 = threading.Thread(target=fourther.run)

    # Jalankan ketiga-tiga thread secara serentak
    thread1.start()
    thread2.start()
    thread3.start()

    # Tunggu sehingga kesemua thread selesai barulah program utama ditutup
    thread1.join()
    thread2.join()
    thread3.join()

    print("\nSemua kerja thread telah selesai!")
```

***Multiprocessing - Parallelism***
How it works: It spawns three entirely separate Python processes, running each class on a different CPU core simultaneously

```
import multiprocessing
import math


# --- Fungsi Pembantu untuk Semak Nombor Perdana ---
def is_prime(n):
    if n <= 1:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False  # Elakkan nombor genap lain

    # Semak pembahagi ganjil sehingga punca kuasa dua n
    for i in range(3, int(math.sqrt(n)) + 1, 2):
        if n % i == 0:
            return False
    return True


# --- Class-Class Utama ---
class SquarePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"Square Prime: {x}^2 = {x**2}")


class CubePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"Cube Prime:   {x}^3 = {x**3}")


class FourthPowerPrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"Fourth Prime: {x}^4 = {x**4}")


# --- Parallel Execution ---
if __name__ == "__main__":
    # Cetus objek
    squarer = SquarePrinter()
    cuber = CubePrinter()
    fourther = FourthPowerPrinter()

    print("Memulakan proses kuasakan nombor perdana secara parallel...\n")

    # Sediakan proses
    p1 = multiprocessing.Process(target=squarer.run)
    p2 = multiprocessing.Process(target=cuber.run)
    p3 = multiprocessing.Process(target=fourther.run)

    # Jalan serentak
    p1.start()
    p2.start()
    p3.start()

    # Tunggu selesai
    p1.join()
    p2.join()
    p3.join()

    print("\nSemua pengiraan nombor perdana selesai!")
```
***Asyncio - Concurrency***
How it works: It runs on a single CPU core using an event loop, explicitly yielding control (await) to switch between classes.
```
import asyncio
import math


# --- Fungsi Pembantu untuk Semak Nombor Perdana ---
def is_prime(n):
    if n <= 1:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False

    for i in range(3, int(math.sqrt(n)) + 1, 2):
        if n % i == 0:
            return False
    return True


# --- Class-Class Utama ---
class SquarePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    async def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"[Async-Task 1] Square Prime: {x}^2 = {x**2}")

            # Setiap 50 nombor, kita serah giliran (yield) kepada event loop
            if x % 50 == 0:
                await asyncio.sleep(0)


class CubePrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    async def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"[Async-Task 2] Cube Prime:   {x}^3 = {x**3}")

            if x % 50 == 0:
                await asyncio.sleep(0)


class FourthPowerPrinter:

    def __init__(self, limit=10000001):
        self.limit = limit

    async def run(self):
        for x in range(self.limit):
            if is_prime(x):
                print(f"[Async-Task 3] Fourth Prime: {x}^4 = {x**4}")

            if x % 50 == 0:
                await asyncio.sleep(0)


# --- Pengurusan Event Loop ---
async def main():
    # Cetus objek
    squarer = SquarePrinter()
    cuber = CubePrinter()
    fourther = FourthPowerPrinter()

    print("Memulakan pengiraan nombor perdana menggunakan Asyncio...\n")

    # asyncio.gather akan mendaftarkan ketiga-tiga coroutine ke dalam event loop
    # dan menjalankan mereka secara konfuren (bergilir-gilir dengan sangat pantas)
    await asyncio.gather(squarer.run(), cuber.run(), fourther.run())

    print("\nSemua tugasan Asyncio telah selesai!")


if __name__ == "__main__":
    # Jalankan function main() di dalam persekitaran async
    asyncio.run(main())
```

