---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0b103513bdcdef42c61172d1cc0ee096264a9559
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521554"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)
Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.  
  
 Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden. Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden. Deshalb schlagen Objektinitialisierer, die öffentlichen Zugriff benötigen, fehl, wenn der Standardkonstruktor als `private` in der Klasse deklariert ist.  
  
 Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren. Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Initialisieren einer Reihe von `StudentName`-Typen mithilfe eines Auflistungsinitialisierers gezeigt. Beachten Sie, dass ein Auflistungsinitialisierer aus einer Reihe von durch Trennzeichen getrennten Objektinitialisierern besteht.  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in Visual Studio erstellt wurde, um den Code auszuführen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
