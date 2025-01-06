### ~~YAML Yet Another Markup Language~~ Yaml Ain't Markup Language

#### What does HTML do ?

Provides structure and hierarchy to web pages

# Then what is YAML

YAML is data format used to exchange data
Similar to xml and JSON
In YAML you can store data but not command

# Defination

Applications written with different technologies or languages which have different Data Structure can transfer data to each other using a common/Standard format . YAML , JSON , And XML are examples of such formats .

#### It is a Data Serializsation Language

- Data Serialization : Translation of Object (Code + Data) into stream of bytes that saves the state of this object in a form that is transmittable . Using Serialization , data can be converted into code and code can be converted into data again

- Used in configuration files in kubernestes , docker , used in logs , caches

#### Benefits of YAML

- Simple and easy to read
- Nice and Strict Syntax
- Most Languages use it
- More powerful when representing complex data
- Parsers etc various tools are available

**_Note: Any JSON input can be converted to YAML output and vice versa_**

## Yaml SYNTAX and data type

Yaml automatically determines data type if not specified

some common data types

```
zero:  !!int 0
positiveNum: !!int 45
negativeNum: !!int -27
commaValue : !!int 245_00_000
```

Lists

```
colors: !!seq
    - red
    - blue
    - green
    - yellow
```

equivalent json

```
{"colors":["red","blue","green","yellow"]}
```

NestedLists

```
student: !!seq
    - marks: !!seq
        - 40
        - 40
        - 60
    - name: !!seq
        - "John"
        - "Doe"
```

```
-
 - Item1
 - Item2
 - Item3

-
 - Item1
 - Item2
 - Item3
```

Treat as single line

```
singleLine: >-
    i am a cs student
    currently learninig devops
    dev
```

#### Reusing properties

```
Likes: &likes
    - fruits : Mango
    - food  : rice

person1:
    - Name : "John"
    <<: *likes
```

Dictionary
```
People:
 -Hammad:
  - Role: Student
  - Age: 20
 -Kunal:
  -Role: Teacher
  -Age: 78
```
