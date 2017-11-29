---
title: "XAML-Namespaces für .NET Framework-XAML-Dienste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: e09279209bf3d6925b61d55d6988b5af658f5aab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>XAML-Namespaces für .NET Framework-XAML-Dienste
Ein XAML-Namespace ist ein Konzept, das bei der Definition eines XML-Namespace wird erweitert. Ähnlich wie ein XML-Namespace können Sie definieren eine XAML-Namespace mit einem `xmlns` Attribut im Markup. Verwendung von XAML-Namespaces werden auch in der XAML-Knotenstream und anderen XAML-Dienste-APIs dargestellt. In diesem Thema wird das Konzept des XAML-Namespace definiert und beschrieben, wie die Verwendung von XAML-Namespaces können definiert werden und von XAML-Schema-Kontexte und andere Aspekte der .NET Framework XAML Services verwendet werden.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML-Namespace und die Verwendung von XAML-Namespace  
 Ein XAML-Namespace ist eine spezielle XML-Namespace an, wie XAML eine spezielle Form des XML-Codes ist und die grundlegende XML-Form für das Markup verwendet. Im Markup, deklarieren Sie einen XAML-Namespace und seine Zuordnung durch eine `xmlns` Attribut auf ein Element angewendet. Die `xmlns` Deklaration vorgenommen werden kann, mit dem gleichen Element, das die Verwendung von XAML-Namespace deklariert ist. Versucht, ein Element eine XAML-Namespace-Deklaration ist gültig für dieses Element, alle Attribute des Elements, und alle untergeordneten Elemente dieses Elements. Attribute können einen XAML-Namespaces, die nicht identisch mit dem Element, das Attribut enthält, ist so lange im Namen des Attributs selbst als Teil der Attributname in Markup verweist das Präfix auf.  
  
 Die Unterscheidung von einem XAML-Namespace im Vergleich zu einem XML-Namespace ist ein XML-Namespace verweisen auf ein Schema verwendet werden kann, oder kann verwendet werden, um einfach Entitäten zu unterscheiden. Für XAML die Typen und Member in XAML verwendeten müssen letztlich in Unterstützungstypen aufgelöst werden, und XML-Schema Konzepte gelten auch auf diese Funktion nicht. Die Verwendung von XAML-Namespace enthält Informationen, die XAML-Schemakontext verfügbar sind, um diese Typzuordnung Ausführen benötigen.  
  
## <a name="xaml-namespace-components"></a>Verwendung von XAML-Namespace Komponenten  
 Die Definition der XAML-Namespace besteht aus zwei Komponenten: einem Präfix und einen Bezeichner. Jede dieser Komponenten sind vorhanden, wenn ein XAML-Namespace im Markup deklariert ist, oder in XAML-Typsystem definiert.  
  
 Das Präfix kann eine beliebige Zeichenfolge sein, mit der [W3C-Namespaces in XML 1.0-Spezifikation](http://go.microsoft.com/fwlink/?LinkID=161735) . Gemäß der Konvention sind die Präfixe in der Regel sehr kurze Zeichenfolgen zu, da das Präfix häufig in einer typischen Markupdatei wiederholt wird. Bestimmte Verwendung von XAML-Namespaces, die in mehreren XAML-Implementierungen verwendet werden sollen, verwenden bestimmte konventionellen Präfixe: Beispielsweise der XAML-Sprachnamespace ist in der Regel zugeordnet mit dem Präfix `x`. Sie können einen XAML-Standardnamespace definieren, in dem das Präfix nicht in der Definition erhält, aber als leere Zeichenfolgen dargestellt, wenn definiert oder von.NET Framework-XAML-Dienste-API abgefragt. Der XAML-Standardnamespace wird in der Regel absichtlich ausgewählt, um eine maximierten Menge der Präfix-verzichten höher stufen Markup durch eine Technologie zur Verwendung von XAML-Implementierung und die Szenarien und Vokabularen.  
  
 Der Bezeichner kann eine beliebige Zeichenfolge sein, mit der [W3C-Namespaces in XML 1.0-Spezifikation](http://go.microsoft.com/fwlink/?LinkID=161735). Gemäß der Konvention werden Bezeichner für die XML-Namespaces oder XAML-Namespaces häufig in URI-Form, in der Regel als Protokoll qualifizierter absoluter URI angegeben. Versionsinformationen, die ein bestimmtes XAML-Vokabular definiert wird häufig als Teil der Pfadzeichenfolge impliziert. Eine zusätzliche Bezeichner Konvention hinter der XML-URI-Konvention fügen Sie XAML-Namespaces hinzu. Bei Verwendung von XAML-Namespaces kommuniziert der Bezeichner, um die Typen aufzulösen, die als Elemente unter diesem XAML-Namespace angegeben werden, oder zum Auflösen von Attributen in Elemente durch einen XAML-Schemakontext erforderlich ist.  
  
 Für die Zwecke der kommunizieren von Informationen, um einen XAML-Schemakontext möglicherweise der Bezeichner für einen XAML-Namespace weiterhin im URI-Format. Allerdings wird in diesem Fall der URI auch als ein übereinstimmender Bezeichner in einer bestimmten Assembly oder eine Liste der Assemblys deklariert. Dies erfolgt in Assemblys durch die Assembly mit Attributierung <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Diese Methode zur Identifizierung des XAML-Namespaces und unterstützt ein CLR-basierten Lösung Verhalten mit Attributen versehenen Assembly wird von der Verwendung von XAML-Standardschemakontext in .NET Framework XAML Services unterstützt. Üblicher, kann diese Konvention für Fälle verwendet werden, in dem der XAML-Schemakontext die CLR beinhaltet oder basiert auf der standardmäßigen XAML-Schemakontext, der zum Lesen von CLR-Attribute von CLR-Assemblys erforderlich ist.  
  
 XAML-Namespaces kann auch durch eine Konvention, die identifiziert werden, die einen CLR-Namespace und eine Assembly Typ definieren zu kommunizieren. Diese Konvention dient in Fällen, denen keine <xref:System.Windows.Markup.XmlnsDefinitionAttribute> namensnennung vorhanden ist, in den Assemblys, die Typen enthalten. Diese Konvention ist möglicherweise komplexer als die URI-Konvention und hat auch potenzielle Mehrdeutigkeit und Duplizierung aus, da es gibt mehrere Möglichkeiten zum Verweisen auf eine Assembly.  
  
 Die einfachste Form eines Bezeichners, der die CLR-Namespace und Assembly-Konvention verwendet lautet wie folgt:  
  
 `clr-namespace:`*ClrnsName* `; assembly=` *AssemblyShortName*  
  
 `clr-namespace:`und `; assembly=` sind Literale Komponenten der Syntax.  
  
 *ClrnsName* ist der Name der Zeichenfolge, die einen CLR-Namespace identifiziert. Dieser Zeichenfolgenname enthält alle internen Punktzeichen (.), die Hinweise zu CLR-Namespace und seine Beziehung zu anderen CLR-Namespaces enthalten.  
  
 *AssemblyShortName* wird der Zeichenfolgennamen einer Assembly, die Typen definiert, die in XAML verwendet werden. Die Typen, die über den deklarierten XAML-Namespace zugegriffen werden von der Assembly definiert werden und insbesondere innerhalb von angegebenen CLR-Namespace deklariert werden voraussichtlich *ClrnsName*. Diese Zeichenfolgennamen entspricht die Informationen in der Regel von gemeldeten <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 Eine vollständige Definition der CLR-Namespace und Assembly Konvention lautet wie folgt:  
  
 `clr-namespace:`*ClrnsName* `; assembly=` *AssemblyName*  
  
 *AssemblyName* stellt eine beliebige Zeichenfolge, die als zulässig ist eine <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> Eingabe. Diese Zeichenfolge enthalten kann, Kultur, öffentlicher Schlüssel oder Versionsinformationen (Definitionen dieser Konzepte sind in einem Referenzthema definiert <xref:System.Reflection.Assembly>). COFF-Format sowie einen Beweis (wie andere Überladungen des verwendeten <xref:System.Reflection.Assembly.Load%2A>) sind irrelevant für die Verwendung von XAML-Assembly laden Zwecke; muss alle Informationen als Zeichenfolge dargestellt werden.  
  
 Angeben eines öffentlichen Schlüssels für die Assembly ist eine nützliche Technik für die Verwendung von XAML-Sicherheit oder zum Entfernen von Mehrdeutigkeiten, der vorhanden sein kann, wenn Assemblys, über den einfachen Namen geladen werden oder in einer Domäne Cache oder die Anwendung bereits vorhanden ist. Weitere Informationen finden Sie unter [XAML-Sicherheitsüberlegungen](../../../docs/framework/xaml-services/xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Verwendung von XAML-Namespace-Deklarationen in der XAML-Dienste-API  
 In der XAML-Dienste-API wird durch eine XAML-Standardnamespace-Deklaration dargestellt eine <xref:System.Xaml.NamespaceDeclaration> Objekt. Wenn Sie einen XAML-Namespace im Code deklarieren, rufen Sie die <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> Konstruktor. Die `ns` und `prefix` Parameter als Zeichenfolgen angegeben werden, und die Eingabe für diese Parameter bereitstellen entspricht die Definition der XAML-Namespacebezeichner und Verwendung von XAML-Namespace-Präfix wie zuvor in diesem Thema angegeben.  
  
 Wenn XAML-Namespaceinformationen im Rahmen eines XAML-Knotenstreams oder durch andere Zugriff auf die Verwendung von XAML-Typsystem überprüfenden <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> meldet den XAML-Namespacebezeichner und <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> meldet die Verwendung von XAML-Namespace-Präfix.  
  
 Die XAML-Namespaceinformationen stehen in einem XAML-Knotenstream als einen XAML-Knoten, der die Entität vorausgeht, für die er gilt. Dies gilt auch für Fälle, in denen die Verwendung von XAML-Namespaceinformationen vor, der `StartObject` des XAML-Stammelements. Weitere Informationen finden Sie unter [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Für viele Szenarien, die .NET Framework-XAML-Dienste-API verwenden, mindestens ein XAML-Standardnamespace-Deklaration muss vorhanden sein, und die Deklaration enthalten oder finden Sie Informationen, die durch einen XAML-Schemakontext verfügbar sein muss. Die Verwendung von XAML-Namespaces geben entweder Assemblys geladen werden oder bei der Auflösung von bestimmten Typen in Namespaces und Assemblys, die bereits geladen oder der XAML-Schemakontext bekannt sind.  
  
 Um einen XAML-Knotenstream zu generieren, muss XAML-Typinformationen über den XAML-Schemakontext verfügbar sein. Die Verwendung von XAML-Typinformationen kann nicht ermittelt werden, ohne zunächst ermittelt den relevanten XAML-Namespace für die einzelnen Knoten zu erstellen. Zu diesem Zeitpunkt werden noch keine Instanzen von Typen erstellt, aber der XAML-Schemakontext Informationen aus der definierenden Assembly und Unterstützungstyp suchen möchten. Angenommen, damit das Markup verarbeitet `<Party><PartyFavor/></Party>`, der XAML-Schemakontext muss in der Lage, den Namen und Typ des bestimmen die `ContentProperty` von `Party`, und daher auch müssen wissen, die XAML-Namespaceinformationen für `Party` und `PartyFavor`. Bei der Verwendung von XAML-Standardschemakontext meldet statische Reflektion ein Großteil der Verwendung von XAML-System Typinformationen, die zum Generieren von XAML-Typknoten im Knotenstream erforderlich ist.  
  
 Um ein Objektdiagramm aus einer XAML-Knotenstream zu generieren, müssen die Verwendung von XAML-Namespacedeklarationen für jedes Präfix XAML im XAML-Knotenstream aufgezeichnet und im ursprünglichen Markup verwendet vorhanden sein. Zu diesem Zeitpunkt Instanzen erstellt werden, und "true" Typzuordnung Verhalten tritt auf.  
  
 Informationen zur Verwendung von XAML-Namespace in Fällen vorab aufgefüllt wird, in dem der XAML-Namespace den XAML-Schemakontext verwenden soll nicht in das Markup definiert, werden sollen ist eine Technik, die Sie verwenden können, deklarieren von XML-Namespacedeklaration in der <xref:System.Xml.XmlParserContext> für eine <xref:System.Xml.XmlReader>. Dann verwenden, die <xref:System.Xml.XmlReader> als Eingabe für einen XAML-Reader-Konstruktor oder <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Zwei andere API, die für die Verwendung von XAML-Namespace in .NET Framework XAML Services Behandlung von relevant sind, sind die Attribute <xref:System.Windows.Markup.XmlnsDefinitionAttribute> und <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Diese Attribute gelten für Assemblys. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>wird durch einen XAML-Schemakontext verwendet, um jede Verwendung von XAML-Namespace-Deklaration zu interpretieren, die einen URI enthält. <xref:System.Windows.Markup.XmlnsPrefixAttribute>wird von Tools verwendet, die XAML ausgeben, sodass ein bestimmter XAML-Namespace mit einem vorhersagbaren Präfix serialisiert werden kann. Weitere Informationen finden Sie unter [XAML-Related CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
