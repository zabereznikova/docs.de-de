---
title: 'Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 0169bfa6eb3ba01a9a88c2b247ad3f78da67d59c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "45964487"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)
*Indizierte Eigenschaften* verbessern die Verarbeitung von COM-Eigenschaften mit Parametern in der C#-Programmierung. Indizierte Eigenschaften arbeiten zusammen mit anderen Funktionen in Visual C#, wie z.B. [benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) und neuen Typinformationen ([dynamisch](../../../csharp/language-reference/keywords/dynamic.md)) und [eingebettete Typinformationen](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), um die Microsoft Office-Programmierung zu verbessern.  
  
 In früheren Versionen von C# waren Methoden nur als Eigenschaften zugänglich, wenn die `get`-Methode keine Parameter und die `set`-Methode nur einen Wertparameter hatte. Allerdings erfüllen nicht alle COM-Eigenschaften diese Einschränkungen. Die Eigenschaft <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> in Excel verfügt über eine `get`-Zugriffsmethode, für die ein Parameter für den Namen des Bereichs erforderlich ist. Früher mussten Sie stattdessen die `get_Range`-Methode verwenden, weil Sie nicht direkt auf die `Range`-Methode zugreifen konnten. Dies wird in folgendem Beispiel veranschaulicht.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 Mit indizierte Eigenschaften können Sie stattdessen Folgendes schreiben:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  Im vorherigen Beispiel wurde auch die Funktion [Optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) verwendet, mit der Sie `Type.Missing` weglassen können.  
  
 Für das Festlegen der `Value`-Eigenschaft eines <xref:Microsoft.Office.Interop.Excel.Range>-Objekts in Visual C# 2008 und früher sind zwei Argumente erforderlich. Eines dieser Argumente stellt ein Argument für einen optionalen Parameter bereit, der den Typ des Bereichswerts angibt. Das andere Argument stellt den Wert für die `Value`-Eigenschaft bereit. In den folgenden Beispielen werden diese Techniken veranschaulicht. Beide legen den Wert der Zelle A1 auf `Name` fest.
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 Mit indizierte Eigenschaften können Sie stattdessen folgenden Code schreiben.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 Sie können nicht Ihre eigenen indizierten Eigenschaften erstellen. Die Funktion unterstützt nur die Nutzung vorhandener indizierter Eigenschaften.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht das vollständige Beispiel. Weitere Informationen zum Einrichten eines Projekts, das auf die Office-API zugreift, finden Sie unter [Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
- [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
- [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
- [Gewusst wie: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
- [Exemplarische Vorgehensweise: Office-Programmierung](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
