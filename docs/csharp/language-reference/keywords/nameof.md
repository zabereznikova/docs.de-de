---
title: nameof (C#-Referenz)
ms.date: 2017-06-16
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- nameof_CSharpKeyword
- nameof
dev_langs:
- CSharp
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: db79af5f38439b881863cf3e03aa0e684ec5cd39
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="nameof-c-reference"></a>nameof (C#-Referenz)

Wird verwendet, um den einfachen (nicht qualifizierten) Zeichenfolgennamen einer Variablen, eines Typs oder eines Members abzurufen.  

Beim Melden von Fehlern im Code, Einbinden von MVC-Links (Model-View-Controller) und Auslösen von durch Eigenschaften geänderten Ereignissen usw. ist es oft erforderlich, den Zeichenfolgennamen einer Methode zu erfassen.  Mithilfe von `nameof` bleibt der Code beim Umbenennen von Definitionen gültig.  Bisher mussten zum Verweisen auf Definitionen Zeichenfolgenliterale verwendet werden; dies ist jedoch fehleranfällig, wenn Codeelemente umbenannt werden, da Tools diese Zeichenfolgenliterale nicht überprüfen können.  
  
 Ein `nameof`-Ausdruck hat die folgende Form:  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a>Wichtige Einsatzbeispiele  
 Diese Beispiele zeigen die wichtigsten Anwendungsfälle für `nameof`.  
  
 Überprüfen von Parametern:  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 MVC-Aktionslinks:  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 INotifyPropertyChanged:  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 XAML-Abhängigkeitseigenschaft:  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 Protokollieren:  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 Attribute:  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a>Beispiele  
 Einige C#-Beispiele:  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
nameof(C) -> "C"  
nameof(C.Method1) -> "Method1"   
nameof(C.Method2) -> "Method2"  
nameof(c.Method1) -> "Method1"   
nameof(c.Method2) -> "Method2"  
nameof(z) -> "z" // inside of Method2 ok, inside Method1 is a compiler error  
nameof(Stuff) = "Stuff"  
nameof(T) -> "T" // works inside of method but not in attributes on the method  
nameof(f) -> "f"  
nameof(f<T>) -> syntax error  
nameof(f<>) -> syntax error  
nameof(Method2()) -> error "This expression does not have a name"  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Argument für `nameof` muss ein einfacher Name, qualifizierter Name, Memberzugriff, Basiszugriff mit angegebenem Member oder dieser Zugriff mit angegebenem Member sein.  Der Argumentausdruck identifiziert eine Codedefinition, wird jedoch niemals ausgewertet.  
  
 Da das Argument syntaktisch ein Ausdruck sein muss, ist vieles unzulässig; eine Auflistung wäre jedoch nicht sinnvoll.  Fehler werden bspw. erzeugt durch: vordefinierte Typen (z. B. `int` oder `void`), auf NULL festlegbare Typen (`Point?`), Arraytypen (`Customer[,]`), Zeigertypen (`Buffer*`), qualifizierte Aliase (`A::B`), ungebundene generische Typen (`Dictionary<,>`), Vorverarbeitungssymbole (`DEBUG`) und Bezeichnungen (`loop:`).  
  
 Wenn Sie den vollqualifizierten Namen abrufen müssen, können Sie den `typeof`-Ausdruck zusammen mit `nameof` verwenden.  Zum Beispiel:
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 Leider ist `typeof` kein konstanter Ausdruck wie `nameof`, sodass `typeof` nicht zusammen mit `nameof` an den gleichen Orten wie `nameof` verwendet werden kann.  Beispielsweise würde Folgendes einen Kompilierungsfehler CS0182 erzeugen:
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 In den Beispielen sehen Sie, dass Sie einen Typnamen verwenden und auf den Namen einer Instanzmethode zugreifen können.  Sie müssen nicht über eine Instanz des Typs verfügen, wie es in ausgewerteten Ausdrücken erforderlich ist.  Die Verwendung des Typnamens kann in einigen Situationen sehr praktisch sein, und da Sie nur auf den Namen verweisen und keine Instanzdaten verwenden, müssen Sie keine Instanzvariable und keinen Ausdruck erfinden.  
  
 Sie können auf die Member einer Klasse in Attributausdrücken in der Klasse verweisen.  
  
 Es gibt keine Möglichkeit, Signaturinformationen wie z. B. „`Method1 (str, str)`“ abzurufen.  Dazu müssen Sie z. B. einen Ausdruck (`Expression e = () => A.B.Method1("s1", "s2")`) verwenden und die MemberInfo aus der resultierenden Ausdrucksbaumstruktur abrufen.  
  
## <a name="language-specifications"></a>Sprachspezifikationen  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 

