---
title: 'Gewusst wie: Definieren von abstrakten Eigenschaften – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie abstrakte Eigenschaften in C# definieren. Das Deklarieren einer abstrakten Eigenschaft bedeutet, dass eine Klasse eine Eigenschaft unterstützt. Die abgeleiteten Klassen implementieren Zugriffsmethoden.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 4db71721495857c634e8090b986704d8a592b4e2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864396"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Gewusst wie: Definieren von abstrakten Eigenschaften (C#-Programmierhandbuch)
Das folgende Beispiel veranschaulicht, wie Sie [abstrakte](../../language-reference/keywords/abstract.md) Eigenschaften definieren: Eine abstrakte Eigenschaftendeklaration stellt keine Implementierung des Eigenschaftenaccessors bereit, sondern deklariert, dass die Klasse Eigenschaften unterstützt, die Accessorenimplementierung jedoch abgeleiteten Klassen überlässt. Das folgende Beispiel veranschaulicht das Implementieren von abstrakten Eigenschaften, die von einer Basisklasse geerbt wurden.  
  
 Dieses Beispiel besteht aus drei Dateien, von denen jede einzeln kompiliert wird, und auf die daraus entstehende Assembly von der nächsten Kompilierung verwiesen wird.  
  
- abstractshape.cs: die `Shape`-Klasse, die eine abstrakte `Area`-Eigenschaft enthält.  
  
- shapes.cs: die Unterklassen der `Shape`-Klasse.  
  
- shapetest.cs: ein Testprogramm zum Anzeigen der Bereiche einiger von `Shape` abgeleiteter Objekte.  
  
 Verwenden Sie den folgenden Befehl, um das Beispiel zu kompilieren:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Dadurch wird die ausführbare Datei „shapetest.exe“ erstellt.  
  
## <a name="example"></a>Beispiel  
 Diese Datei deklariert die `Shape`-Klasse, die die `Area`-Eigenschaft des Typs `double` enthält.  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- Modifizierer der Eigenschaft sind in der Deklaration der Eigenschaft selbst platziert. Zum Beispiel:  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- Wenn Sie eine abstrakte Eigenschaft deklarieren (z.B. `Area` in diesem Beispiel), geben Sie lediglich an, welche Eigenschaftenaccessoren verfügbar sind, implementieren diese jedoch nicht. In diesem Beispiel ist nur ein [get](../../language-reference/keywords/get.md)-Accessor verfügbar, die Eigenschaft ist also schreibgeschützt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt drei Unterklassen von `Shape` und wie sie die `Area`-Eigenschaft überschreiben, um ihre eigene Implementierung bereitzustellen.  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt ein Testprogramm, das eine Reihe abgeleiteter `Shape`-Objekte erstellt und deren Bereiche ausdruckt.  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Abstrakte und versiegelte Klassen und Klassenmember](./abstract-and-sealed-classes-and-class-members.md)
- [Eigenschaften](./properties.md)
