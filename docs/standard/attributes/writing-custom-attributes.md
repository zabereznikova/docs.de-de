---
title: Verfassen von benutzerdefinierten Attributen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114d24c1fc523d5501deb4aa17f9541c5a918276
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="writing-custom-attributes"></a>Verfassen von benutzerdefinierten Attributen
Zum Entwerfen eigener, benutzerdefinierter Attribute brauchen Sie nicht viele neue Konzepte zu beherrschen. Wenn Sie mit objektorientierter Programmierung vertraut sind und wissen, wie Klassen entworfen werden, haben Sie bereits den größten Teil der Kenntnisse, die Sie benötigen. Benutzerdefinierte Attribute sind im Wesentlichen traditionelle Klassen, die sich direkt oder indirekt aus <xref:System.Attribute?displayProperty=nameWithType> ableiten. Genau wie traditionelle Klassen enthalten benutzerdefinierte Attribute Methoden zum Speichern und Abrufen von Daten.  
  
 Die wichtigsten Schritte beim ordnungsgemäßen Entwerfen von benutzerdefinierten Attributklassen sind die folgenden:  
  
-   [Anwenden des AttributeUsage-Attributs](#cpconapplyingattributeusageattribute)  
  
-   [Deklarieren der Attributklasse](#cpcondeclaringattributeclass)  
  
-   [Deklarieren von Konstruktoren](#cpcondeclaringconstructors)  
  
-   [Deklarieren von Eigenschaften](#cpcondeclaringproperties)  
  
 In diesem Abschnitt wird jeder dieser Schritte beschrieben, den Schluss bildet ein [Beispiel für ein benutzerdefiniertes Attribut](#cpconcustomattributeexample).  
  
<a name="cpconapplyingattributeusageattribute"></a>   
## <a name="applying-the-attributeusageattribute"></a>Anwenden des AttributeUsage-Attributs  
 Die Deklaration eines benutzerdefinierten Attributs beginnt mit dem **AttributeUsage-Attribut**, das einige der Hauptmerkmale Ihrer Attributklasse definiert. Sie können beispielsweise angeben, ob das Attribut von anderen Klassen geerbt werden kann, oder festlegen, auf welche Elemente das Attribut angewendet werden kann. Das folgende Codefragment zeigt, wie das **AttributeUsage-Attribut**verwendet wird.  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 Das <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> weist drei Member auf, die für die Erstellung von benutzerdefinierten Attributen wichtig sind: [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2)und [AllowMultiple](#cpconwritingcustomattributesanchor3).  
  
<a name="cpconwritingcustomattributesanchor1"></a>   
### <a name="attributetargets-member"></a>AttributeTargets-Member  
 Im vorherigen Beispiel wird **AttributeTargets.All** angegeben, was darauf hinweist, dass dieses Attribut auf alle Programmelemente angewendet werden kann. Alternativ können Sie **AttributeTargets.Class**angeben und so festlegen, dass Ihr Attribut nur auf eine Klasse angewendet werden kann, oder **AttributeTargets.Method**, was angibt, dass Ihr Attribut nur auf eine Methode angewendet werden kann. Alle Programmelemente können in dieser Weise für die Beschreibung durch ein benutzerdefiniertes Attribut gekennzeichnet werden.  
  
 Sie können auch mehrere Instanzen von <xref:System.AttributeTargets>übergeben. Das folgende Codefragment gibt an, dass ein benutzerdefiniertes Attribut auf beliebige Klassen oder Methoden angewendet werden kann.  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
<a name="cpconwritingcustomattributesanchor2"></a>   
### <a name="inherited-property"></a>Inherited Property  
 Die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>-Eigenschaft gibt an, ob das Attribut von Klassen geerbt werden kann, die von den Klassen abgeleitet werden, auf die das Attribut angewendet wird. Diese Eigenschaft akzeptiert die Kennzeichen **true** (den Standardwert) oder **false** . Beispielsweise hat im folgenden Beispiel `MyAttribute` für <xref:System.AttributeUsageAttribute.Inherited%2A> den Standardwert **true**, während `YourAttribute` den <xref:System.AttributeUsageAttribute.Inherited%2A> -Standardwert **false**aufweist.  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 Die beiden Attribute werden dann auf eine Methode in der Basisklasse `MyClass`angewendet.  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 Schließlich wird die Klasse `YourClass` von der Basisklasse `MyClass`geerbt. Die Methode `MyMethod` zeigt `MyAttribute`, aber nicht `YourAttribute`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
<a name="cpconwritingcustomattributesanchor3"></a>   
### <a name="allowmultiple-property"></a>AllowMultiple-Eigenschaft  
 Die <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType>-Eigenschaft gibt an, ob mehrere Instanzen eines Attributs für ein Element vorhanden sein können. Wenn es auf **true**festgelegt ist, sind mehrere Instanzen zulässig; bei **false** (dem Standardwert) ist nur eine Instanz erlaubt.  
  
 Im folgenden Beispiel weist `MyAttribute` für <xref:System.AttributeUsageAttribute.AllowMultiple%2A> den Standardwert **false**auf, während `YourAttribute` den Wert **true**hat.  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 Wenn mehrere Instanzen dieser Attribute angewendet werden, führt `MyAttribute` zu einem Compilerfehler. Das folgende Codebeispiel zeigt die gültige Verwendung von `YourAttribute` und die ungültige Verwaltung von `MyAttribute`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 Wenn sowohl die <xref:System.AttributeUsageAttribute.AllowMultiple%2A> -Eigenschaft als auch die <xref:System.AttributeUsageAttribute.Inherited%2A> -Eigenschaft auf **true**festgelegt sind, kann eine Klasse, die von einer anderen Klasse geerbt wurde, ein Attribut erben, und zugleich kann in der gleichen untergeordneten Klasse eine weitere Instanz des gleichen Attributs angewendet werden. Wenn <xref:System.AttributeUsageAttribute.AllowMultiple%2A> auf **false**festgelegt ist, werden die Werte aller Attribute in der übergeordneten Klasse durch neue Instanzen der gleichen Attribute in der untergeordneten Klasse überschrieben.  
  
<a name="cpcondeclaringattributeclass"></a>   
## <a name="declaring-the-attribute-class"></a>Deklarieren der Attributklasse  
 Nach dem Anwenden von <xref:System.AttributeUsageAttribute>können Sie beginnen, die Einzelheiten Ihres Attributs zu definieren. Die Deklaration einer Attributklasse ähnelt der Deklaration einer traditionellen Klasse, wie im folgenden Code zu sehen.  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 Diese Attibutdefinition veranschaulicht die folgenden Punkte:  
  
-   Attributklassen müssen als öffentliche Klassen deklariert werden.  
  
-   Gemäß Konvention endet der Name der Attributklasse mit dem Wort **Attribute**. Dies ist zwar nicht erforderlich, die Einhaltung dieser Konvention empfiehlt sich aber aus Gründen der besseren Übersicht. Wenn das Attribut angewendet wird, ist die Aufnahme des Wortes „Attribute“ optional.  
  
-   Alle Attributklassen müssen direkt oder indirekt von **System.Attribute**erben.  
  
-   In Microsoft Visual Basic müssen alle Attributklassen über das Attribut **AttributeUsageAttribute** verfügen.  
  
<a name="cpcondeclaringconstructors"></a>   
## <a name="declaring-constructors"></a>Deklarieren von Konstruktoren  
 Attribute werden in der gleichen Weise wie traditionelle Klassen mit Konstruktoren initialisiert. Das folgende Codefragment stellt ein Beispiel für einen typischen Attributkonstruktor dar. Dieser öffentliche Konstruktor akzeptiert einen Parameter und legt seinen Wert auf eine Membervariable fest.  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 Sie können den Konstruktor überladen, um verschiedene Kombinationen von Werten zu ermöglichen. Wenn Sie darüber hinaus eine [Eigenschaft](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52) für Ihre benutzerdefinierte Attributklasse definieren, können Sie eine Kombination aus benannten und Positionsparametern zum Initialisieren des Attributs verwenden. Normalerweise definieren Sie alle erforderlichen Parameter als Positionsparameter und alle optionalen Parameter als benannt. In diesem Fall kann das Attribut nicht ohne den erforderlichen Parameter initialisiert werden. Alle anderen Parameter sind optional. Beachten Sie, dass in Visual Basic die Konstruktoren für eine Attributklasse kein ParamArray-Argument verwenden sollten.  
  
 Das folgende Codebeispiel zeigt, wie ein Attribut, das den oben angegebenen Konstruktor verwendet, mithilfe von optionalen und erforderlichen Parametern angewendet werden kann. Es wird angenommen, dass das Attribut einen erforderlichen Booleschen Wert und eine optionale Zeichenfolgeneigenschaft aufweist.  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
<a name="cpcondeclaringproperties"></a>   
## <a name="declaring-properties"></a>Deklarieren von Eigenschaften  
 Wenn Sie einen benannten Parameter definieren oder eine einfache Möglichkeit zum Zurückgeben der von Ihrem Attribut gespeicherten Werte bereitstellen möchten, deklarieren Sie eine [Eigenschaft](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52). Attributeigenschaften müssen als öffentliche Entitäten mit einer Beschreibung des zurückgegebenen Datentyps deklariert werden. Definieren Sie die Variable, die den Wert der Eigenschaft enthalten soll, und ordnen Sie sie den Methoden **get** und **set** zu. Das folgende Codebeispiel veranschaulicht, wie eine einfache Eigenschaft in Ihrem Attribut implementiert wird.  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
<a name="cpconcustomattributeexample"></a>   
## <a name="custom-attribute-example"></a>Beispiel für ein benutzerdefiniertes Attribut  
 Dieser Abschnitt beinhaltet die Informationen aus den vorhergehenden Abschnitten und zeigt das Entwerfen eines einfachen Attributs, das Informationen über den Autor eines Codeabschnitts dokumentiert. Das Attribut in diesem Beispiel speichert den Namen und die Qualifikation des Programmierers und gibt an, ob der Code überprüft wurde. Es verwendet drei private Variablen zum Speichern der eigentlichen, zu speichernden Werte. Jede Variable wird durch eine öffentliche Eigenschaft dargestellt, die zum Abrufen und Festlegen der Werte verwendet wird. Schließlich wird der Konstruktor mit zwei erforderlichen Parametern definiert.  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 Sie können das Attribut mit seinem vollständigen Namen `DeveloperAttribute`oder mit seinem abgekürzten Namen `Developer`auf eine der folgenden Weisen anwenden.  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 Im ersten Beispiel wird das Attribut nur mit den erforderlichen benannten Parametern angewendet, während das zweite Beispiel die Anwendung des Attributs mit den erforderlichen und den optionalen Parametern zeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Attribute?displayProperty=nameWithType>  
 <xref:System.AttributeUsageAttribute>  
 [Attribute](../../../docs/standard/attributes/index.md)
