---
title: XAML-Namespaces für .NET XAML-Dienste
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433061"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>XAML-Namespaces für .NET XAML-Dienste
Ein XAML-Namespace ist ein Konzept, das die Definition eines XML-Namespace erweitert. Ähnlich wie bei einem XML-Namespace können Sie einen `xmlns` XAML-Namespace mithilfe eines Attributs in Markup definieren. XAML-Namespaces werden auch im XAML-Knotenstream und anderen XAML Services-APIs dargestellt. In diesem Thema wird das XAML-Namespacekonzept definiert und beschrieben, wie XAML-Namespaces definiert und von XAML-Schemakontexten und anderen Aspekten von .NET XAML Services verwendet werden können.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML-Namespace und XAML-Namespace  
 Ein XAML-Namespace ist ein spezieller XML-Namespace, ebenso wie XAML eine spezialisierte Xml-Form ist und das grundlegende XML-Formular für sein Markup verwendet. In Markup deklarieren Sie einen XAML-Namespace und dessen Zuordnung über ein `xmlns` Attribut, das auf ein Element angewendet wird. Die `xmlns` Deklaration kann in demselben Element vorgenommen werden, in dem der XAML-Namespace deklariert ist. Eine XAML-Namespacedeklaration für ein Element ist für dieses Element, alle Attribute dieses Elements und alle untergeordneten Elemente dieses Elements gültig. Attribute können einen XAML-Namespace verwenden, der nicht mit dem Element identisch ist, das das Attribut enthält, solange der Attributname selbst auf das Präfix als Teil seines Attributnamens in Markup verweist.  
  
 Die Unterscheidung eines XAML-Namespace im Vergleich zu einem XML-Namespace besteht darin, dass ein XML-Namespace verwendet werden kann, um auf ein Schema zu verweisen oder einfach entitätsverschiedene Elemente zu unterscheiden. Für XAML müssen die in XAML verwendeten Typen und Member letztendlich in Sicherungstypen aufgelöst werden, und XML-Schemakonzepte gelten nicht gut für diese Funktion. Der XAML-Namespace enthält Informationen, über die der XAML-Schemakontext verfügen muss, um diese Typzuordnung durchführen zu können.  
  
## <a name="xaml-namespace-components"></a>XAML-Namespacekomponenten  
 Die XAML-Namespacedefinition besteht aus zwei Komponenten: einem Präfix und einem Bezeichner. Jede dieser Komponenten ist vorhanden, wenn ein XAML-Namespace in Markup deklariert oder im XAML-Typsystem definiert wird.  
  
 Das Präfix kann eine beliebige Zeichenfolge sein, wie sie von den [W3C-Namespaces in der XML 1.0-Spezifikation](https://www.w3.org/TR/REC-xml-names/)zulässig ist. Gemäß der Konvention sind die Präfixe in der Regel kurze Zeichenfolgen, da das Präfix in einer typischen Markupdatei mehrmals wiederholt wird. Bestimmte XAML-Namespaces, die in mehreren XAML-Implementierungen verwendet werden sollen, verwenden bestimmte herkömmliche Präfixe. Beispielsweise wird der XAML-Sprach-XAML-Namespace in `x`der Regel mit dem Präfix zugeordnet. Sie können einen standardmäßigen XAML-Namespace definieren, bei dem das Präfix nicht in der Definition angegeben ist, aber als leere Zeichenfolge dargestellt wird, wenn by.NET XAML Services-API definiert oder abgefragt wird. In der Regel wird der standardmäßige XAML-Namespace bewusst gewählt, um eine maximierte Menge an präfixauslassendem Markup durch eine XAML-implementierende Technologie und ihre Szenarien und Vokabeln zu fördern.  
  
 Der Bezeichner kann eine beliebige Zeichenfolge sein, wie sie von den [W3C-Namespaces in der XML 1.0-Spezifikation](https://www.w3.org/TR/REC-xml-names/)zulässig ist. Gemäß der Konvention werden Bezeichner für XML-Namespaces oder XAML-Namespaces häufig in URI-Form angegeben, in der Regel als protokollqualifizierter absoluter URI. Häufig werden Versionsinformationen, die ein bestimmtes XAML-Vokabular definieren, als Teil der Pfadzeichenfolge impliziert. XAML-Namespaces fügen eine zusätzliche Bezeichnerkonvention hinzu, die über die XML-URI-Konvention hinausgeht. Bei XAML-Namespaces übermittelt der Bezeichner Informationen, die von einem XAML-Schemakontext benötigt werden, um die Typen aufzulösen, die als Elemente unter diesem XAML-Namespace angegeben sind, oder um Attribute für Member aufzulösen.  
  
 Zum Kommunizieren von Informationen an einen XAML-Schemakontext ist der Bezeichner für einen XAML-Namespace möglicherweise weiterhin in URI-Form. In diesem Fall wird der URI jedoch auch als übereinstimmender Bezeichner in einer bestimmten Assembly oder Liste von Assemblys deklariert. Dies geschieht in Assemblys, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>indem die Assembly mit zugeordnet wird. Diese Methode zum Identifizieren des XAML-Namespace und zur Unterstützung eines CLR-basierten Typauflösungsverhaltens in der attributierten Assembly wird vom standardmäßigen XAML-Schemakontext in .NET XAML Services unterstützt. Im Allgemeinen kann diese Konvention für Fälle verwendet werden, in denen der XAML-Schemakontext die CLR enthält oder auf dem Standardmäßigen XAML-Schemakontext basiert, der zum Lesen von CLR-Attributen aus CLR-Assemblys erforderlich ist.  
  
 XAML-Namespaces können auch durch eine Konvention identifiziert werden, die einen CLR-Namespace und eine typdefinierende Assembly kommuniziert. Diese Konvention wird in <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Fällen verwendet, in denen in den Assemblys, die Typen enthalten, keine Zuordnung vorhanden ist. Diese Konvention ist potenziell komplexer als die URI-Konvention und hat auch das Potenzial für Mehrdeutigkeit und Duplizierung, da es mehrere Möglichkeiten gibt, auf eine Assembly zu verweisen.  
  
 Die einfachste Form eines Bezeichners, der den CLR-Namespace und die Assemblykonvention verwendet, ist wie folgt:  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:`und `; assembly=` sind literale Komponenten der Syntax.  
  
 *clrnsName* ist der Zeichenfolgenname, der einen CLR-Namespace identifiziert. Dieser Zeichenfolgenname enthält alle internen Punktzeichen (.), die Hinweise auf den CLR-Namespace und seine Beziehung zu anderen CLR-Namespaces enthalten.
  
 *assemblyShortName* ist der Zeichenfolgenname einer Assembly, die Typen definiert, die in XAML nützlich sind. Es wird erwartet, dass die Typen, auf die über den deklarierten XAML-Namespace zugegriffen werden soll, von der Assembly definiert und innerhalb des clR-Namespace deklariert werden, der von *clrnsName*angegeben wird. Dieser Zeichenfolgenname verläuft in der <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>Regel parallel zu den Informationen, die von gemeldet werden.  
  
 Eine vollständigere Definition der CLR-Namespace- und Assemblykonvention lautet wie folgt:  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *assemblyName* stellt jede Zeichenfolge dar, die als <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> Eingabe zulässig ist. Diese Zeichenfolge kann Kultur-, öffentliche Schlüssel- oder Versionsinformationen enthalten (Definitionen <xref:System.Reflection.Assembly>dieser Konzepte sind im Referenzthema für definiert). COFF-Format und Beweise (wie von <xref:System.Reflection.Assembly.Load%2A>anderen Überladungen von verwendet) sind für das Laden von XAML-Baugruppen nicht relevant; Alle Ladeinformationen müssen als Zeichenfolge dargestellt werden.  
  
 Das Angeben eines öffentlichen Schlüssels für die Assembly ist eine nützliche Methode für die XAML-Sicherheit oder zum Entfernen möglicher Mehrdeutigkeiten, die vorhanden sein können, wenn Assemblys mit einem einfachen Namen geladen werden oder in einem Cache oder einer Anwendungsdomäne vorhanden sind. Weitere Informationen finden Sie unter [XAML-Sicherheitsüberlegungen](security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML-Namespace-Deklarationen in der XAML Services-API  
 In der XAML Services-API wird eine XAML-Namespacedeklaration durch ein <xref:System.Xaml.NamespaceDeclaration> Objekt dargestellt. Wenn Sie einen XAML-Namespace im Code <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> deklarieren, rufen Sie den Konstruktor auf. Die `ns` `prefix` und Parameter werden als Zeichenfolgen angegeben, und die Eingabe, die für diese Parameter bereitgestellt werden soll, entspricht der Definition von XAML-Namespace-Idund und XAML-Namespacepräfix, wie zuvor in diesem Thema angegeben.  
  
 Wenn Sie XAML-Namespaceinformationen als Teil eines XAML-Knotenstreams oder über einen <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> anderen Zugriff auf das XAML-Typsystem untersuchen, meldet der XAML-Namespacebezeichner und <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> meldet das XAML-Namespacepräfix.  
  
 In einem XAML-Knotenstream können die XAML-Namespaceinformationen als XAML-Knoten angezeigt werden, der der Entität vorangeht, auf die sie angewendet wird. Dies schließt Fälle ein, in denen die `StartObject` XAML-Namespaceinformationen vor dem des XAML-Stammelements stehen. Weitere Informationen finden Sie unter [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Für viele Szenarien, die die .NET XAML Services-API verwenden, ist davon auszugehen, dass mindestens eine XAML-Namespacedeklaration vorhanden ist, und die Deklaration muss informationen enthalten oder auf informationen verweisen, die für einen XAML-Schemakontext erforderlich sind. Die XAML-Namespaces müssen entweder Assemblys angeben, die geladen werden sollen, oder beim Auflösen bestimmter Typen in Namespaces und Assemblys helfen, die bereits geladen sind oder vom XAML-Schemakontext bekannt sind.  
  
 Um einen XAML-Knotenstream zu generieren, müssen XAML-Typinformationen über den XAML-Schemakontext verfügbar sein. Die XAML-Typinformationen können nicht ermittelt werden, ohne vorher den relevanten XAML-Namespace für jeden zu erstellenden Knoten zu bestimmen. Zu diesem Zeitpunkt werden noch keine Instanzen von Typen erstellt, aber der XAML-Schemakontext muss möglicherweise Informationen aus der definierenden Assembly und dem Sicherungstyp suchen. Um das `<Party><PartyFavor/></Party>`Markup verarbeiten zu können, muss der XAML-Schemakontext beispielsweise den `ContentProperty` `Party`Namen und Typ des von bestimmen können `Party` und `PartyFavor`daher auch die XAML-Namespaceinformationen für und kennen. Im Fall des standardmäßigen XAML-Schemakontexts meldet die statische Reflektion einen Großteil der Systeminformationen vom XAML-Typ, die zum Generieren von XAML-Typknoten im Knotenstream erforderlich sind.  
  
 Um ein Objektdiagramm aus einem XAML-Knotenstream zu generieren, müssen XAML-Namespacedeklarationen für jedes XAML-Präfix vorhanden sein, das im ursprünglichen Markup verwendet und im XAML-Knotenstream aufgezeichnet wird. An diesem Punkt werden Instanzen erstellt, und es tritt ein echtes Typzuordnungsverhalten auf.  
  
 Wenn Sie XAML-Namespaceinformationen vorab auffüllen müssen, kann in Fällen, in denen der XAML-Namespace, den der XAML-Schemakontext verwenden soll, <xref:System.Xml.XmlParserContext> nicht <xref:System.Xml.XmlReader>im Markup definiert sind, eine Technik, die Sie verwenden können, darin, XML-Namespacedeklarationen im für zu deklarieren. Verwenden Sie <xref:System.Xml.XmlReader> diese als Eingabe für einen XAML-Readerkonstruktor oder <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Zwei weitere APIs, die für die XAML-Namespacebehandlung in .NET XAML Services relevant sind, sind die Attribute <xref:System.Windows.Markup.XmlnsDefinitionAttribute> und <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Diese Attribute gelten für Assemblys. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>wird von einem XAML-Schemakontext verwendet, um jede XAML-Namespacedeklaration zu interpretieren, die einen URI enthält. <xref:System.Windows.Markup.XmlnsPrefixAttribute>wird von Tools verwendet, die XAML aussenden, sodass ein bestimmter XAML-Namespace mit einem vorhersagbaren Präfix serialisiert werden kann. Weitere Informationen finden Sie unter [XAML-verknüpfte CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](clr-attributes-with-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](understanding-xaml-node-stream-structures-and-concepts.md)
