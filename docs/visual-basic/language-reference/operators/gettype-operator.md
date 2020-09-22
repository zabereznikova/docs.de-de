---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 9ff207ea4f2b89ea30eb8f46a3e640ccf3789974
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867005"
---
# <a name="gettype-operator-visual-basic"></a>GetType-Operator (Visual Basic)

Gibt ein- <xref:System.Type> Objekt für den angegebenen Typ zurück. Das- <xref:System.Type> Objekt stellt Informationen über den Typ bereit, z. b. seine Eigenschaften, Methoden und Ereignisse.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---|---|  
|`typename`|Der Name des Typs, für den Sie Informationen wünschen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Der- `GetType` Operator gibt das- <xref:System.Type> Objekt für den angegebenen zurück `typename` . Sie können den Namen eines beliebigen definierten Typs in übergeben `typename` . Hierzu gehören folgende Elemente:  
  
- Beliebige Visual Basic Datentyp, z `Boolean` . b `Date` . oder.  
  
- Alle .NET Framework Klassen, Strukturen, Module oder Schnittstellen, z <xref:System.ArgumentException?displayProperty=nameWithType> . b <xref:System.Double?displayProperty=nameWithType> . oder.  
  
- Alle Klassen, Strukturen, Module oder Schnittstellen, die von der Anwendung definiert werden.  
  
- Ein beliebiges Array, das von Ihrer Anwendung definiert wird.  
  
- Jeder Delegat, der von der Anwendung definiert wird.  
  
- Eine beliebige Enumeration, die von Visual Basic, dem .NET Framework oder der Anwendung definiert wird.  
  
 Wenn Sie das Typobjekt einer Objektvariablen erhalten möchten, verwenden Sie die- <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.  
  
 Der- `GetType` Operator kann in den folgenden Situationen nützlich sein:  
  
- Sie müssen zur Laufzeit auf die Metadaten für einen Typ zugreifen. Das <xref:System.Type> -Objekt stellt Metadaten wie Typmember und Bereitstellungs Informationen bereit. Dies ist z. b. erforderlich, um eine Assembly widerzuspiegeln. Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Sie möchten zwei Objekt Verweise vergleichen, um festzustellen, ob Sie auf Instanzen desselben Typs verweisen. Wenn dies der Fall ist, `GetType` gibt Verweise auf dasselbe <xref:System.Type> Objekt zurück.  
  
## <a name="example"></a>Beispiel  

 Die folgenden Beispiele zeigen den `GetType` verwendeten Operator.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
