---
title: GetType-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38a984dce44133936f7f163e6afb20f0f336377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gettype-operator-visual-basic"></a>GetType-Operator (Visual Basic)
Gibt eine <xref:System.Type> Objekt für den angegebenen Typ. Die <xref:System.Type> Objekt enthält Informationen über den Typ, z. B. seine Eigenschaften, Methoden und Ereignisse.  
  
## <a name="syntax"></a>Syntax  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---|---|  
|`typename`|Der Name des Typs für die Sie Informationen wünschen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `GetType` Operator gibt den <xref:System.Type> für das angegebene Objekt `typename`. Sie können den Namen eines beliebigen definierten Typs in übergeben `typename`. Hierzu gehören folgende Elemente:  
  
-   Alle Visual Basic-Datentyp, wie z. B. `Boolean` oder `Date`.  
  
-   Alle .NET Framework-Klasse, Struktur, Modul oder Schnittstelle, wie z. B. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.  
  
-   Eine beliebige Klasse, Struktur, Modul oder Schnittstelle, die von der Anwendung definiert.  
  
-   Alle von der Anwendung definiertes Array.  
  
-   Alle von der Anwendung definierten Delegaten.  
  
-   Eine Enumeration von Visual Basic, .NET Framework oder der Anwendung definiert.  
  
 Wenn Sie das Typobjekt einer Objektvariablen abrufen möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.  
  
 Die `GetType` Operator kann in folgenden Situationen nützlich sein:  
  
-   Sie müssen die Metadaten für einen Typ zur Laufzeit zugreifen. Die <xref:System.Type> Objekt liefert Metadaten, z. B. Typmember und Bereitstellungsinformationen. Dies ist erforderlich, z. B. über eine Assembly widerspiegeln. Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Vergleichen von zwei Objektverweise, um festzustellen, ob sie auf Instanzen des gleichen Typs verweisen möchten. Wenn dies der Fall, `GetType` gibt Verweise auf die gleiche <xref:System.Type> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die `GetType` Operator verwendet.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
