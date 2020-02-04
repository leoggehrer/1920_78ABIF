### Technik/Generische Typen (Seidl)

- Erklären Sie die Technik 'Generizität' und erläutern Sie die Verwendung dieser Technik (konstruieren Sie ein einfaches Beispiel).

In der Programmierung kommt es immer wieder vor das bestimmte standardisierte Strukturen, immer wieder mit verschiedenen Typen benötigt werden.

Ein Beispiel in unserem Programm benötigen wir sowohl eine List für Strings, als auch für Pupils, integers und viele mehr.

Statt nun die Struktur für jeden Typ extra anzulegen, greift man daher auf die Verwendung von Generics zurück um den Typ austauschen zu können.

```
class List<T> {
  T get(int index);
  T add(T element);
  bool remove(T element);
  ...
}
```

- Generizität ist eine sehr junge Programmiertechnik. Wie konnte man vor Einführung dieser Technik bestimmte Merkmale dieser Technik dennoch nachbilden (erläutern Sie dies anhand der abstrakten Datenstruktur 'Stack').

In C Beispielsweise konnten void Zeiger auf alle Datentypen verweisen, auf diese Weise konnte der Datentyp ebenfalls ausgetauscht werden.

```
struct Node {
  Node* next
  void* value;
}
struct Stack{
  Node* anker;
  
  void push(void* element){
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode.value = element;
    if(anker==NULL) anker = newNode;
    else{
      newNode.next = anker;
      anker = newNode;
    }
  }
  void* pop(){
    Node* tmp = anker;
    void* value = NULL;
    if(anker != NULL){
      anker = anker.next;
      value = tmp.value;
      free(tmp);
    }
    return value;
  }
}
```

- Was sind Einschränkungen und welche Bedeutung haben diese im Bezug auf Generische Typen (skizzieren Sie ein Beispiel)?
  Das Problem hierbei bei der Zeiger bassierten Verknüpfung ist, das der Aufrufer wissen muss welchen Typ er im endeffekt erhält um wieder
  auf den korrekten Datentyp umwandeln zu können.
