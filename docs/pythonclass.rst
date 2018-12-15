==================
Class
==================

Cấu trúc một class trong python như sau

.. code-block:: python

    class Dog:

        # Class Attribute
        species = 'mammal'

        # Initializer / Instance Attributes
        def __init__(self, name, age):
            self.name = name
            self.age = age
        
        # Override __str__ method
        def __str__(self):
            return 'Dog has name = {}, age = {}'.format(self.name, self.age)

        def __getitem__(self):
            return self.name;

    # Instantiate the Dog object
    jake = Dog("Jake", 7)
    doug = Dog("Doug", 4)
    william = Dog("William", 5)

    dog_data = {}
    dog_list = []
    dog_list.append(jake)
    dog_list.append(doug)
    dog_list.append(william)

    d = dict(enumerate(dog_list))

    # Determine the oldest dog
    def get_biggest_number(*args):
        return max(args)


    # Output
    print("The oldest dog is {} years old.".format(
        get_biggest_number(jake.age, doug.age, william.age)))

-  ``__getitem__``

Xem ví dụ sau đây:

.. code-block:: python

    class Building(object):
        def __init__(self, floors):
            self._floors = [None]*floors
        def occupy(self, floor_number, data):
            self._floors[floor_number] = data
        def get_floor_data(self, floor_number):
            return self._floors[floor_number]
    building1 = Building(4) # Construct a building with 4 floors
    building1.occupy(0, 'Reception')
    building1.occupy(1, 'ABC Corp')
    building1.occupy(2, 'DEF Inc')

Nếu không có ``__getitem__`` thì mỗi khi để get thuộc tính bạn cần phải gọi method như sau:

.. code-block:: python

   print( building1.get_floor_data(2) )

Như thế thì nhìn không đẹp tí nào. Nếu thêm phương thức ``__getitem__`` thì bạn có thể gọi thuộc tính sành điệu hơn rất
nhiều (gọi bằng index giống như array)

.. code-block:: python

    class Building(object):
        def __init__(self, floors):
            self._floors = [None]*floors
        def occupy(self, floor_number, data):
            self._floors[floor_number] = data
        def get_floor_data(self, floor_number):
            return self._floors[floor_number]
        def __getitem__(self, floor_number):
            return self._floors[floor_number]

    building1 = Building(4) # Construct a building with 4 floors
    building1.occupy(0, 'Reception')
    building1.occupy(1, 'ABC Corp')
    building1.occupy(2, 'DEF Inc')
    print(building1[1])

    # Output
    # ABC Corp
