---
title: GetType-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840320"
---
# <a name="gettype-operator-visual-basic"></a>GetType-Operator (Visual Basic)
Gibt eine <xref:System.Type> Objekt für den angegebenen Typ. Die <xref:System.Type> Objekt enthält Informationen über die Art, wie z. B. die Eigenschaften, Methoden und Ereignisse.  
  
## <a name="syntax"></a>Syntax  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---|---|  
|`typename`|Der Name des Typs für die Sie Informationen wünschen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `GetType` -Operator gibt die <xref:System.Type> -Objekt für die angegebene `typename`. Sie können den Namen eines beliebigen definierten Typs in übergeben `typename`. Hierzu gehören folgende Elemente:  
  
-   Geben Sie alle Visual Basic-Daten, z. B. `Boolean` oder `Date`.  
  
-   Alle .NET Framework-Klasse, Struktur, Modul oder Schnittstelle, wie z. B. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.  
  
-   Jede Klasse, Struktur, Modul oder Schnittstelle, die von der Anwendung definiert.  
  
-   Ein Array, das von der Anwendung definiert.  
  
-   Jeder Delegat, der von der Anwendung definiert wird.  
  
-   Enumerationen von Visual Basic, .NET Framework oder der Anwendung definiert.  
  
 Wenn Sie das Type-Objekt einer Objektvariablen abrufen möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.  
  
 Die `GetType` Operator kann in folgenden Situationen nützlich sein:  
  
-   Sie müssen die Metadaten für einen Typ zur Laufzeit zugreifen. Die <xref:System.Type> Objekt liefert Metadaten wie z. B. Typmember und Bereitstellungsinformationen. Sie benötigen diesen, z. B. über eine Assembly widerspiegeln. Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Sie möchten vergleichen zwei Objektverweise, um festzustellen, ob sie mit Instanzen des gleichen Typs verweisen. Wenn dies der Fall, `GetType` gibt Verweise auf die gleiche <xref:System.Type> Objekt.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen die `GetType` -Operator in verwenden.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Siehe auch

- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
