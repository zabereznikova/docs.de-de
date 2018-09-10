---
title: 'Gewusst wie: Überschreiben der ToString-Methode (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: b047efb9215675b8c3dfb75438a6dbbc4e6f92d0
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084172"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Gewusst wie: Überschreiben der ToString-Methode (C#-Programmierhandbuch)
In C# erben alle Klassen oder Strukturen implizit die <xref:System.Object>-Klasse. Deshalb erhält jedes Objekt in C# die <xref:System.Object.ToString%2A>-Methode, die eine Zeichenfolgenrepräsentation dieses Objekts zurückgibt. Alle Variablen des Typs `int` verfügen z.B über eine `ToString`-Methode, die es ihnen ermöglicht, ihren Inhalt als Zeichenfolge zurückzugeben:  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen, um Informationen zum Typ an den Clientcode bereitzustellen.  
  
 Weitere Informationen zum Verwenden von Formatzeichenfolgen und anderen Arten von benutzerdefinierten Formaten mit der `ToString`-Methode finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
>  Wenn Sie sich entschieden haben, welche Informationen Sie über diese Methode bereitstellen möchten, beziehen Sie auch mit ein, ob Ihre Klasse oder Struktur von nicht vertrauenswürdigem Code verwendet wird. Achten Sie darauf, dass Sie keine Informationen bereitstellen, die von böswilligem Code ausgenutzt werden könnten.  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a>Außerkraftsetzen der ToString-Methode in Ihrer Klasse oder Struktur  
  
1.  Deklarieren Sie eine `ToString`-Methode mit folgenden Modifizierern und Rückgabetypen:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.  
  
     Im folgenden Beispiel wird der Name der Klasse neben den für eine bestimmte Instanz der Klasse spezifischen Daten zurückgegeben.  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Sie können die `ToString`-Methode auch wie im folgenden Beispiel gezeigt prüfen:  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IFormattable>  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)  
- [string](../../../csharp/language-reference/keywords/string.md)  
- [new](../../../csharp/language-reference/keywords/new.md)  
- [override](../../../csharp/language-reference/keywords/override.md)  
- [virtual](../../../csharp/language-reference/keywords/virtual.md)  
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
