---
title: 'Gewusst wie: Überschreiben der ToString-Methode – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie die ToString-Methode in C# überschreiben. Jede Klasse oder Struktur erbt ein Objekt und ruft „ToString“ ab. Dadurch wird eine Zeichenfolgendarstellung dieses Objekts zurückgegeben.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: de56ea10ea15f497f9375c2449acbae1d0c8978a
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099262"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Gewusst wie: Überschreiben der ToString-Methode (C#-Programmierhandbuch)

In C# erben alle Klassen oder Strukturen implizit die <xref:System.Object>-Klasse. Deshalb erhält jedes Objekt in C# die <xref:System.Object.ToString%2A>-Methode, die eine Zeichenfolgenrepräsentation dieses Objekts zurückgibt. Alle Variablen des Typs `int` verfügen z.B über eine `ToString`-Methode, die es ihnen ermöglicht, ihren Inhalt als Zeichenfolge zurückzugeben:  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen, um Informationen zum Typ an den Clientcode bereitzustellen.  
  
 Weitere Informationen zum Verwenden von Formatzeichenfolgen und anderen Arten von benutzerdefinierten Formaten mit der `ToString`-Methode finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
> Wenn Sie sich entschieden haben, welche Informationen Sie über diese Methode bereitstellen möchten, beziehen Sie auch mit ein, ob Ihre Klasse oder Struktur von nicht vertrauenswürdigem Code verwendet wird. Achten Sie darauf, dass Sie keine Informationen bereitstellen, die von böswilligem Code ausgenutzt werden könnten.  
  
Außerkraftsetzen der `ToString`-Methode in Ihrer Klasse oder Struktur:
  
1. Deklarieren Sie eine `ToString`-Methode mit folgenden Modifizierern und Rückgabetypen:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.  
  
     Im folgenden Beispiel wird der Name der Klasse neben den für eine bestimmte Instanz der Klasse spezifischen Daten zurückgegeben.  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     Sie können die `ToString`-Methode auch wie im folgenden Beispiel gezeigt prüfen:  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IFormattable>
- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Zeichenfolgen](../strings/index.md)
- [string](../../language-reference/builtin-types/reference-types.md)
- [override](../../language-reference/keywords/override.md)
- [virtual](../../language-reference/keywords/virtual.md)
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
