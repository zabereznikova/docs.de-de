---
title: 'Vorgehensweise: Definieren von abstrakten Eigenschaften – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: ab846f423631c8238ff9a516f95d32ff32bd0335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616334"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Vorgehensweise: Definieren von abstrakten Eigenschaften (C#-Programmierhandbuch)
Das folgende Beispiel veranschaulicht, wie Sie [abstrakte](../../../csharp/language-reference/keywords/abstract.md) Eigenschaften definieren: Eine abstrakte Eigenschaftendeklaration stellt keine Implementierung des Eigenschaftenaccessors bereit, sondern deklariert, dass die Klasse Eigenschaften unterstützt, die Accessorenimplementierung jedoch abgeleiteten Klassen überlässt. Das folgende Beispiel veranschaulicht das Implementieren von abstrakten Eigenschaften, die von einer Basisklasse geerbt wurden.  
  
 Dieses Beispiel besteht aus drei Dateien, von denen jede einzeln kompiliert wird, und auf die daraus entstehende Assembly von der nächsten Kompilierung verwiesen wird.  
  
-   abstractshape.cs: die `Shape`-Klasse, die eine abstrakte `Area`-Eigenschaft enthält.  
  
-   shapes.cs: die Unterklassen der `Shape`-Klasse.  
  
-   shapetest.cs: ein Testprogramm zum Anzeigen der Bereiche einiger von `Shape` abgeleiteter Objekte.  
  
 Verwenden Sie den folgenden Befehl, um das Beispiel zu kompilieren:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Dadurch wird die ausführbare Datei „shapetest.exe“ erstellt.  
  
## <a name="example"></a>Beispiel  
 Diese Datei deklariert die `Shape`-Klasse, die die `Area`-Eigenschaft des Typs `double` enthält.  
  
 [!code-csharp[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]  
  
-   Modifizierer der Eigenschaft sind in der Deklaration der Eigenschaft selbst platziert. Beispiel:  
  
    ```csharp  
    public abstract double Area  
    ```  
  
-   Wenn Sie eine abstrakte Eigenschaft deklarieren (z.B. `Area` in diesem Beispiel), geben Sie lediglich an, welche Eigenschaftenaccessoren verfügbar sind, implementieren diese jedoch nicht. In diesem Beispiel ist nur ein [get](../../../csharp/language-reference/keywords/get.md)-Accessor verfügbar, die Eigenschaft ist also schreibgeschützt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt drei Unterklassen von `Shape` und wie sie die `Area`-Eigenschaft überschreiben, um ihre eigene Implementierung bereitzustellen.  
  
 [!code-csharp[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt ein Testprogramm, das eine Reihe abgeleiteter `Shape`-Objekte erstellt und deren Bereiche ausdruckt.  
  
 [!code-csharp[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
