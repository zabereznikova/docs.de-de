---
title: GetType-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592150"
---
# <a name="gettype-operator-visual-basic"></a>GetType-Operator (Visual Basic)
Gibt ein <xref:System.Type>-Objekt für den angegebenen Typ zurück. Das <xref:System.Type>-Objekt enthält Informationen über den Typ, z. b. seine Eigenschaften, Methoden und Ereignisse.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---|---|  
|`typename`|Der Name des Typs, für den Sie Informationen wünschen.|  
  
## <a name="remarks"></a>Hinweise  
 Der `GetType`-Operator gibt das <xref:System.Type>-Objekt für den angegebenen `typename` zurück. Sie können den Namen eines beliebigen definierten Typs in `typename` übergeben. Hierzu gehören folgende Elemente:  
  
- Alle Visual Basic Datentyps, z. b. `Boolean` oder `Date`.  
  
- Alle .NET Framework Klassen, Strukturen, Module oder Schnittstellen, z. b. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.  
  
- Alle Klassen, Strukturen, Module oder Schnittstellen, die von der Anwendung definiert werden.  
  
- Ein beliebiges Array, das von Ihrer Anwendung definiert wird.  
  
- Jeder Delegat, der von der Anwendung definiert wird.  
  
- Eine beliebige Enumeration, die von Visual Basic, dem .NET Framework oder der Anwendung definiert wird.  
  
 Wenn Sie das Typobjekt einer Objektvariablen erhalten möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType>-Methode.  
  
 Der `GetType`-Operator kann in den folgenden Situationen nützlich sein:  
  
- Sie müssen zur Laufzeit auf die Metadaten für einen Typ zugreifen. Das <xref:System.Type>-Objekt stellt Metadaten wie Typmember und Bereitstellungs Informationen bereit. Dies ist z. b. erforderlich, um eine Assembly widerzuspiegeln. Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Sie möchten zwei Objekt Verweise vergleichen, um festzustellen, ob Sie auf Instanzen desselben Typs verweisen. Wenn dies der Fall ist, gibt `GetType` Verweise auf dasselbe <xref:System.Type>-Objekt zurück.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen den verwendeten `GetType`-Operator.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Siehe auch

- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
