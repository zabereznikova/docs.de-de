---
title: Reflektion und generische Typen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic types
- reflection, generic types
- type arguments
- generics [.NET Framework], reflection
- viewing type information
- type information, viewing
- types, generic
- type parameters
ms.assetid: f7180fc5-dd41-42d4-8a8e-1b34288e06de
ms.openlocfilehash: 0a7d38c8177aa8f2c5f45dcc62a0ae6e5aaca2a7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975448"
---
# <a name="reflection-and-generic-types"></a>Reflektion und generische Typen
Aus Sicht der Reflektion besteht der Unterschied zwischen einem generischen und einem normalen Typ darin, dass ein generischer Typ mit einem Typparameterset (bei einer generischen Typdefinition) oder mit Typargumenten (bei einem konstruierten Typ) verknüpft ist. Auf dieselbe Art unterscheidet sich eine generische Methode von einer normalen Methode.  
  
 Es gibt zwei wichtige Schlüssel für das Verständnis des Umgangs von Reflektion mit generischen Typen und Methoden:  
  
- Die Typparameter der generischen Typdefinitionen und generischen Methodendefinitionen werden durch Instanzen der <xref:System.Type> -Klasse dargestellt.  
  
    > [!NOTE]
    > Viele Eigenschaften und Methoden des <xref:System.Type> -Objekts weisen ein anderes Verhalten auf, wenn ein <xref:System.Type> -Objekt einen generischen Typparameter darstellt. Diese Unterschiede werden in den Themen zu Eigenschaften und Methoden erläutert. Beispielsweise unter <xref:System.Type.IsAutoClass%2A> und <xref:System.Type.DeclaringType%2A>. Darüber hinaus sind einige Member nur gültig, wenn ein <xref:System.Type> -Objekt einen generischen Typparameter darstellt. Ein Beispiel finden Sie unter <xref:System.Type.GetGenericTypeDefinition%2A>.  
  
- Wenn eine Instanz des <xref:System.Type> -Objekts einen generischen Typ darstellt, enthält es ein Array von Typen, das die Typparameter (bei generischen Typdefinitionen) oder die Typargumente (bei konstruierten Typen) darstellt. Gilt auch für eine Instanz der <xref:System.Reflection.MethodInfo> -Klasse, die eine generische Methode darstellt.  
  
 Reflektion stellt <xref:System.Type>- und <xref:System.Reflection.MethodInfo>-Methoden bereit, mit denen Sie auf das Array von Typparametern zugreifen und ermitteln können, ob eine <xref:System.Type>-Instanz einen Typparameter oder einen tatsächlichen Typ darstellt.  
  
 Ein Codebeispiel zur Erläuterung der hier dargestellten Methoden finden Sie unter [How to: Examine and Instantiate Generic Types with Reflection (Vorgehensweise: Erkennen und Bearbeiten von generischen Typen)](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 Bei der folgenden Erläuterung wird davon ausgegangen, dass Sie mit der Terminologie von Generics vertraut sind, d. h. Sie kennen beispielsweise den Unterschied zwischen Typparametern und Typargumenten sowie zwischen offenen und geschlossenen konstruierten Typen. Weitere Informationen finden Sie unter [Generics](../../standard/generics/index.md).  

## <a name="is-this-a-generic-type-or-method"></a>Ist dies ein generischer Typ oder eine generische Methode?  
 Verwenden Sie beim Überprüfen eines unbekannten durch eine Instanz der <xref:System.Type>-Klasse dargestellten Typs die <xref:System.Type.IsGenericType%2A> -Eigenschaft, um zu ermitteln, ob es sich beim unbekannten Typ um einen generischen Typ handelt. Die Eigenschaft gibt `true` zurück, wenn es sich um einen generischen Typ handelt. Verwenden Sie dementsprechend beim Überprüfen einer unbekannten durch eine Instanz der <xref:System.Reflection.MethodInfo> -Klasse dargestellten Methode die <xref:System.Reflection.MethodBase.IsGenericMethod%2A> -Eigenschaft, um zu ermitteln, ob es sich bei der unbekannten Methode um eine generische Methode handelt.  
  
### <a name="is-this-a-generic-type-or-method-definition"></a>Ist dies eine generische Typ- oder Methodendefinition?  
 Mit der <xref:System.Type.IsGenericTypeDefinition%2A> -Eigenschaft können Sie bestimmen, ob ein <xref:System.Type> -Objekt eine generische Typdefinition darstellt, und mit der <xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A> -Methode, ob ein <xref:System.Reflection.MethodInfo> -Objekt eine generische Methodendefinition darstellt.  
  
 Generische Typ- und Methodendefinitionen sind Vorlagen, aus denen instanziierbare Typen erstellt werden. Generische Typen in der .NET Framework-Klassenbibliothek wie <xref:System.Collections.Generic.Dictionary%602>sind generische Typdefinitionen.  
  
### <a name="is-the-type-or-method-open-or-closed"></a>Ist der Typ bzw. die Methode offen oder geschlossen?  
 Ein generischer Typ oder eine generische Methode ist geschlossen, wenn alle Typparameter, u. a. Typparameter aller einschließenden Typen durch instanziierbare Typen ersetzt wurden. Sie können nur eine Instanz eines generischen Typs erstellen, wenn er geschlossen ist. Die <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> -Eigenschaft gibt `true` zurück, wenn ein Typ offen ist. Bei Methoden erfüllt die <xref:System.Reflection.MethodBase.ContainsGenericParameters%2A?displayProperty=nameWithType> -Methode die gleiche Funktion.   

## <a name="generating-closed-generic-types"></a>Generieren geschlossener generischer Typen  
 Wenn Sie bereits über eine generische Typ- oder Methodendefinition verfügen, können Sie mit der <xref:System.Type.MakeGenericType%2A> -Methode einen geschlossenen generischen Typ erstellen oder mit der <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> -Methode ein <xref:System.Reflection.MethodInfo> -Objekt für eine geschlossene generische Methode erstellen.  
  
### <a name="getting-the-generic-type-or-method-definition"></a>Abrufen der generischen Typ- bzw. Methodendefinition  
 Wenn Sie über einen offenen generischen Typ- bzw. eine offene generische Methode verfügen, die keine generische Typ- bzw. Methodendefinition ist, können Sie keine Instanzen davon erstellen und keine fehlenden Typparameter bereitstellen. Sie müssen über eine generische Typ- oder Methodendefinition verfügen. Verwenden Sie zum Abrufen der generischen Typdefinition die <xref:System.Type.GetGenericTypeDefinition%2A> -Methode oder die <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> -Methode zum Abrufen der generischen Methodendefinition.  
  
 Wenn Sie über ein <xref:System.Type> -Objekt verfügen, das ein `Dictionary<int, string>` -Objekt (`Dictionary(Of Integer, String)` in Visual Basic) darstellt und den `Dictionary<string, MyClass>`-Typ erstellen möchten, können Sie mit der <xref:System.Type.GetGenericTypeDefinition%2A> -Methode ein <xref:System.Type> -Objekt abrufen, das `Dictionary<TKey, TValue>` darstellt, und dann mit der <xref:System.Type.MakeGenericType%2A> -Methode ein <xref:System.Type> -Objekt erstellen, das `Dictionary<int, MyClass>`darstellt.  
  
 Ein Beispiel für einen offenen generischen Typ, der kein generischer Typ ist, finden Sie unter „Typparameter oder Typargument“ im weiteren Verlauf dieses Themas.   

## <a name="examining-type-arguments-and-type-parameters"></a>Überprüfen von Typargumenten und Typparametern  
 Verwenden Sie zum Abrufen eines Arrays von <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> -Objekten, das die Typparameter oder Typargumente eines generischen Typs darstellt, die <xref:System.Type> -Methode und die <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> -Methode, um diesen Vorgang für eine generische Methode auszuführen.  
  
 Wenn Sie wissen, das ein <xref:System.Type> -Objekt einen Typparameter darstellt, kann Reflektion eine Antwort auf viele weitere Fragen bieten. Sie können die Quelle, Position und Einschränkungen des Typparameters bestimmen.  
  
### <a name="type-parameter-or-type-argument"></a>Typparameter oder Typargument  
 Verwenden Sie die <xref:System.Type.IsGenericParameter%2A> -Eigenschaft zum Bestimmen, ob ein bestimmtes Element des Arrays ein Typparameter oder Typargument ist. Die <xref:System.Type.IsGenericParameter%2A> -Eigenschaft ist `true` , wenn das Element ein Typparameter ist.  
  
 Bei einem generischen Typ kann es sich auch um einen offenen Typ handeln, wenn dieser keine generische Typdefinition ist. In diesem Fall verfügt er über eine Mischung aus Typargumenten und Typparametern. Im folgenden Code leitet sich beispielsweise die `D` -Klasse von einem Typ ab, der durch das Ersetzen des zweiten Typparameters von `D` mit dem ersten Typparameter von `B`erstellt wurde.  
  
```csharp  
class B<T, U> {}  
class D<V, W> : B<int, V> {}  
```  
  
```vb  
Class B(Of T, U)  
End Class  
Class D(Of V, W)  
    Inherits B(Of Integer, V)  
End Class  
```  
  
```cpp  
generic<typename T, typename U> ref class B {};  
generic<typename V, typename W> ref class D : B<int, V> {};  
```  
  
 Wenn Sie ein <xref:System.Type> -Objekt erhalten, das ein `D<V, W>` ist und die <xref:System.Type.BaseType%2A> -Eigenschaft zum Abrufen des Basistyps verwenden, ist das resultierende `type B<int, V>` -Objekt ein offener Typ, der jedoch keine generische Typdefinition darstellt.  
  
### <a name="source-of-a-generic-parameter"></a>Quelle eines generischen Parameters  
 Ein generischer Typparameter kann von einem überprüften Typ, einschließenden Typ oder von einer generischen Methode stammen. Die Quelle des generischen Typparameters kann folgendermaßen bestimmt werden:  
  
- Verwenden Sie zuerst die <xref:System.Type.DeclaringMethod%2A> -Eigenschaft, um zu ermitteln, ob der Typparameter von einer generischen Methode stammt. Wenn der Eigenschaftswert kein NULL-Verweis ist (`Nothing` in Visual Basic), ist die Quelle eine generische Methode.  
  
- Wenn die Quelle keine generische Methode ist, verwenden Sie die <xref:System.Type.DeclaringType%2A> -Eigenschaft zum Bestimmen des generischen Typs, zu dem der generische Typparameter gehört.  
  
 Wenn der Typparameter zu einer generischen Methode gehört, gibt die <xref:System.Type.DeclaringType%2A> -Eigenschaft den Typ zurück, der die generische irrelevante Methode deklariert hat.  
  
### <a name="position-of-a-generic-parameter"></a>Position eines generischen Parameters  
 In seltenen Fällen ist es erforderlich, die Position eines Typparameters in der Typparameterliste seiner deklarierenden Klasse zu ermitteln. Angenommen Sie verfügen über ein <xref:System.Type> -Objekt, das den `B<int, V>` -Typ aus dem vorherigen Beispiel darstellt. Mit der <xref:System.Type.GetGenericArguments%2A> -Methode erhalten Sie eine Liste von Typargumenten. Beim Überprüfen des `V` -Objekts können Sie dann die <xref:System.Type.DeclaringMethod%2A> - und <xref:System.Type.DeclaringType%2A> -Eigenschaften verwenden, um die Herkunft dieses Objekts zu bestimmen. Sie können dann mithilfe der <xref:System.Type.GenericParameterPosition%2A> -Eigenschaft seine Position in der Typparameterliste ermitteln, in dem es definiert wurde. In diesem Beispiel befindet sich `V` an Position 0 (null) in der Typparameterliste, in der das Objekt definiert wurde.  
  
### <a name="base-type-and-interface-constraints"></a>Basistyp und Schnittstelleneinschränkungen  
 Verwenden Sie die <xref:System.Type.GetGenericParameterConstraints%2A> -Methode, um die Basistypeinschränkung und Schnittstelleneinschränkungen eines Typparameters abzurufen. Die Reihenfolge der Elemente des Arrays spielt keine Rolle. Ein Element stellt eine Schnittstelleneinschränkung dar, wenn es ein Schnittstellentyp ist.  
  
### <a name="generic-parameter-attributes"></a>Generische Parameterattribute  
 Die <xref:System.Type.GenericParameterAttributes%2A> -Eigenschaft ruft einen <xref:System.Reflection.GenericParameterAttributes> -Wert ab, der die Varianz (Kovarianz oder Kontravarianz) und die besonderen Einschränkungen eines Typparameters angibt.  
  
#### <a name="covariance-and-contravariance"></a>Kovarianz und Kontravarianz  
 Zum Bestimmen, ob ein Typparameter kovariant oder kontravariant ist, können Sie  die <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> -Maske auf den von der <xref:System.Reflection.GenericParameterAttributes> -Eigenschaft zurückgegebenen <xref:System.Type.GenericParameterAttributes%2A> -Wert anwenden. Wenn das Ergebnis <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>ist, ist der Typparameter invariant. Siehe [Kovarianz und Kontravarianz](../../standard/generics/covariance-and-contravariance.md).  
  
#### <a name="special-constraints"></a>Besondere Einschränkungen  
 Wenden Sie zum Bestimmen von besonderen Einschränkungen eines Typparameters die <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> -Maske auf den von der <xref:System.Reflection.GenericParameterAttributes> -Eigenschaft zurückgegebenen <xref:System.Type.GenericParameterAttributes%2A> -Wert an. Wenn das Ergebnis <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>ist, gibt es keine besonderen Einschränkungen. Die Einschränkungen eines Typparameters können ein Verweistyp, ein Werttyp, der keine NULL-Werte zulässt, und ein parameterloser Konstruktor sein.    

## <a name="invariants"></a>Invarianten  
 Eine Tabelle der invarianten Bedingungen für allgemeine Begriffe in Reflektion für generische Typen finden Sie unter <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>. Weitere Begriffe, die im Zusammenhang mit generischen Methoden stehen, finden Sie unter <xref:System.Reflection.MethodBase.IsGenericMethod%2A?displayProperty=nameWithType>.  

## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[How to: Examine and Instantiate Generic Types with Reflection (Vorgehensweise: Erkennen und Bearbeiten von generischen Typen)](how-to-examine-and-instantiate-generic-types-with-reflection.md)|Veranschaulicht die Verwendung von Eigenschaften und Methoden der <xref:System.Type>- und <xref:System.Reflection.MethodInfo>-Objekte zum Untersuchen generischer Typen.|  
|[Generics](../../standard/generics/index.md)|Beschreibt das Genericsfeature und seine Unterstützung in .NET Framework.|  
|[Gewusst wie: Definieren eines generischen Typs mit Reflektionsausgabe](how-to-define-a-generic-type-with-reflection-emit.md)|Veranschaulicht die Verwendung der Reflektionsausgabe zum Generieren generischer Typen in dynamischen Assemblys.|  
|[Anzeigen von Typinformationen](viewing-type-information.md)|Beschreibt die <xref:System.Type>-Klasse und stellt Codebeispiele bereit, die zeigen, wie <xref:System.Type> mit verschiedenen Reflektionsklassen verwendet wird, um Informationen zu Konstruktoren, Methoden, Feldern, Eigenschaften und Ereignissen abzurufen.|
