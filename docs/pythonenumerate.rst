==================
Enumerate
==================

Cách sử dụng enumerate

Với list:

.. code-block:: python

    for counter, value in enumerate(some_list):
        print(counter, value)

Tạo tuple với index từ list:

.. code-block:: python

    my_list = ['apple', 'banana', 'grapes', 'pear']
    counter_list = list(enumerate(my_list, 1))
    print(counter_list)
    # Output: [(1, 'apple'), (2, 'banana'), (3, 'grapes'), (4, 'pear')]

``enumerate`` còn có thêm cả optional parameter để cài offset

.. code-block:: python

    my_list = ['apple', 'banana', 'grapes', 'pear']
    for c, value in enumerate(my_list, 1):
    print(c, value)

    # Output:
    # 1 apple
    # 2 banana
    # 3 grapes
    # 4 pear

.. code-block:: bat

    lazygit
