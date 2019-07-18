---
title: XAML-Namespaces für .NET Framework-XAML-Dienste
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: dc2c424306b9ebd705f2541266e4b1e3afe94547
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938774"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>XAML-Namespaces für .NET Framework-XAML-Dienste
Ein XAML-Namespace ist ein Konzept, das auf der Definition eines XML-Namespaces erweitert. Ähnlich wie ein XML-Namespace, können Sie definieren eine XAML-Namespace mit einem `xmlns` Attribut im Markup. XAML-Namespaces werden auch in der XAML-Knotenstream und andere XAML-Dienste-APIs dargestellt. In diesem Thema das Konzept des XAML-Namespace definiert und beschreibt, wie XAML-Namespaces können definiert werden und von XAML-Schema-Kontexten und andere Aspekte der .NET Framework-XAML-Dienste verwendet werden.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML-Namespace und XAML-Namespace  
 Ein XAML-Namespace ist eine spezielle XML-Namespace, wie XAML eine spezielle Form von XML ist und die grundlegende XML-Form für das Markup verwendet. Im Markup, deklarieren Sie einen XAML-Namespace und seine Zuordnung durch eine `xmlns` Attribut auf ein Element angewendet. Die `xmlns` Deklaration vorgenommen werden kann, mit dem gleichen Element, das in der XAML-Namespace deklariert wird. Eine XAML-Namespacedeklaration auf ein Element ist für dieses Element, das alle Attribute des Elements, und alle untergeordneten Elemente dieses Elements gültig. Attribute können eine XAML-Namespaces, die nicht identisch mit dem Element, das Attribut enthält, sofern die Attributnamen selbst als Teil des Namens Attribut im Markup verweist das Präfix auf.  
  
 Der Unterschied im Vergleich zu einem XML-Namespace eines XAML-Namespace besteht, dass ein XML-Namespace kann verwendet werden, um ein Schema zu verweisen, oder kann verwendet werden, um einfach Entitäten zu unterscheiden. Für XAML die Typen und Member, wie in XAML verwendet, müssen schließlich in Unterstützungstypen aufgelöst werden, und XML-Schema-Konzepte gelten auch für diese Funktion nicht. Der XAML-Namespace enthält Informationen, die der XAML-Schemakontext sein, um diese Typzuordnung ausführen muss.  
  
## <a name="xaml-namespace-components"></a>Komponenten der XAML-Namespace  
 Die Definition der XAML-Namespace besteht aus zwei Komponenten: einem Präfix und einen Bezeichner. Jede dieser Komponenten sind vorhanden, wenn ein XAML-Namespace, die im Markup deklariert oder in der XAML-Typsystem definiert.  
  
 Das Präfix kann eine beliebige Zeichenfolge sein, wie zulässig der [W3C-Namespaces in XML 1.0-Spezifikation](https://go.microsoft.com/fwlink/?LinkID=161735) . Gemäß der Konvention sind die Präfixe in der Regel sehr kurze Zeichenfolgen zu, da das Präfix oft in einer typischen Markupdatei wiederholt wird. Bestimmte XAML-Namespaces, die in mehrere XAML-Implementierungen verwendet werden sollen, verwenden bestimmte konventionellen Präfixe. Z. B. XAML-Namespace der XAML-Sprache in der Regel zugeordnet wird mit dem Präfix `x`. Sie können einen XAML-Standardnamespace definieren, in dem das Präfix in der Definition nicht angegeben wird, aber als leere Zeichenfolge dargestellt wird, wenn definiert oder von.NET Framework-XAML-Dienste-API abgefragt. Der XAML-Standardnamespace ist in der Regel absichtlich getroffen, um eine maximierten Datenmenge über das Präfix weggelassen höher stufen Markup durch eine XAML-Implementierung von Technologie und die Szenarien und Vokabularen.  
  
 Der Bezeichner kann eine beliebige Zeichenfolge sein, wie zulässig der [W3C-Namespaces in XML 1.0-Spezifikation](https://go.microsoft.com/fwlink/?LinkID=161735). Gemäß der Konvention werden Bezeichner für XML-Namespaces oder XAML-Namespaces oft im URI-Format, in der Regel als Protokoll vollqualifizierten absoluten URI angegeben. Versionsinformationen, die ein bestimmtes XAML-Vokabular definiert wird häufig als Teil der Path-Zeichenfolge impliziert. Hinzufügen von XAML-Namespaces eine zusätzlichen Bezeichner Konvention über die XML-URI-Konvention. Für XAML-Namespaces kommuniziert der Bezeichner für Informationen, die von einem XAML-Schemakontext benötigt wird, um die Typen aufzulösen, die als Element unter diesem XAML-Namespace angegeben werden, oder zum Auflösen von Attributen in Elemente.  
  
 Bei der Weitergabe von Informationen zu einem XAML-Schemakontext wird möglicherweise der Bezeichner für einen XAML-Namespace weiterhin im URI-Format. Allerdings ist in diesem Fall der URI auch als übereinstimmender Bezeichner in einer bestimmten Assembly oder eine Liste der Assemblys deklariert. Dies erfolgt in Assemblys durch die Attributierung der Assembly mit <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Diese Methode zum Identifizieren des XAML-Namespace und ein CLR-basierten Lösung Verhalten in der attributierten Assembly unterstützt wird von der Standard-XAML-Schemakontext in .NET Framework-XAML-Dienste unterstützt. Üblicher, diese Konvention kann für Fälle verwendet werden können, in dem der XAML-Schemakontext die CLR beinhaltet, oder basiert auf der Standard XAML-Schemakontext, der zum Lesen von CLR-Attribute von CLR-Assemblys erforderlich ist.  
  
 XAML-Namespaces können auch durch eine Konvention identifiziert werden, die einen CLR-Namespace und einer Assembly Typ definieren zu kommunizieren. Diese Konvention dient in Fällen, denen keine <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Attribution vorhanden ist, in den Assemblys, die Typen enthalten. Diese Konvention ist möglicherweise komplexer als die URI-Konvention, und es verfügt auch über das Potenzial für Mehrdeutigkeit und Duplizierung, da es gibt mehrere Möglichkeiten zum Verweisen auf eine Assembly.  
  
 Die einfachste Form eines Bezeichners, die die CLR-Namespace und Assembly-Konvention verwendet lautet wie folgt aus:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` und `; assembly=` sind Literale Komponenten der Syntax.  
  
 *ClrnsName* lautet die Zeichenfolge, die einen CLR-Namespace identifiziert. Dieser Zeichenfolgenname enthält alle internen Punktzeichen (.), die Hinweise zu den CLR-Namespace und seine Beziehung zu anderen CLR-Namespaces zu bieten.  
  
 *AssemblyShortName* ist von der Zeichenfolgennamen einer Assembly, die Typen definiert, die in XAML nützlich sind. Die Typen, die über den deklarierten XAML-Namespace zugegriffen werden von der Assembly definiert werden und insbesondere deklariert werden, in der CLR-Namespace, der anhand des erwartet *ClrnsName*. Diese Namen gleicht die Informationen in der Regel von gemeldeten <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 Eine vollständige Definition der CLR-Namespace und Assembly Konvention lautet wie folgt aus:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *AssemblyName* stellt eine beliebige Zeichenfolge, die als gültig ist ein <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> Eingabe. Diese Zeichenfolge enthalten kann, Kultur, PublicKey oder Versionsinformationen (Definitionen dieser Konzepte werden in die Referenz für definiert <xref:System.Reflection.Assembly>). COFF Format und Beweise (von andere Überladungen verwendet <xref:System.Reflection.Assembly.Load%2A>) sind nicht relevant für XAML-assamblys Zwecke; alle lastinformationen muss als Zeichenfolge dargestellt werden.  
  
 Angeben eines öffentlichen Schlüssels für die Assembly ist eine nützliche Technik für die XAML-Sicherheit oder Beseitigung möglichen Mehrdeutigkeiten, der vorhanden sein kann, wenn Assemblys, über den einfachen Namen geladen werden oder in einer Domäne Cache oder die Anwendung bereits vorhanden. Weitere Informationen finden Sie unter [XAML-Sicherheitsüberlegungen](xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML-Namespace-Deklarationen in der XAML-Services-API  
 In der XAML-Dienste-API wird durch eine XAML-Namespacedeklaration dargestellt eine <xref:System.Xaml.NamespaceDeclaration> Objekt. Wenn Sie eine XAML-Namespaces im Code deklarieren, rufen Sie die <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> Konstruktor. Die `ns` und `prefix` Parameter werden als Zeichenfolgen angegeben, und die Eingabe für diese Parameter bereitstellen die Definition der XAML-Namespacebezeichner und XAML-Namespacepräfix entspricht, wie zuvor in diesem Thema bereitgestellt.  
  
 Wenn Sie als Teil eines XAML-Knotenstreams oder über Zugriff auf die XAML-Typsystem, die anderen XAML-Namespaceinformationen untersuchen <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> meldet den XAML-Namespacebezeichner und <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> meldet das XAML-Namespace-Präfix.  
  
 Die XAML-Namespaceinformationen darf in einem XAML-Knotenstream als XAML-Knoten, die die Entität vorangestellt ist, auf die es angewendet. Dies schließt Fälle, in denen die XAML-Namespaceinformationen vor, der `StartObject` des XAML-Stammelements. Weitere Informationen finden Sie unter [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Für viele Szenarien, die .NET Framework-XAML-Dienste-API verwenden, mindestens ein XAML-Namespacedeklaration muss vorhanden sein, und die Deklaration muss enthalten oder verweisen auf Informationen, die von einem XAML-Schemakontext erforderlich ist. Die XAML-Namespaces müssen entweder angeben, Assemblys geladen werden, oder bei der Auflösung von bestimmten Typen in Namespaces und Assemblys, die bereits geladen oder der XAML-Schemakontext bekannt sind.  
  
 Um einen XAML-Knotenstream zu generieren, muss XAML-Typinformationen durch den XAML-Schemakontext verfügbar sein. Die Informationen der XAML-Typ kann nicht bestimmt werden, ohne zuerst ermittelt, den entsprechenden XAML-Namespace für jeden Knoten zu erstellen. An diesem Punkt keine Instanzen von Typen noch erstellt werden, aber der XAML-Schemakontext müssen, um Informationen aus der definierenden Assembly und den Unterstützungstyp zu suchen. Z. B. um das Markup zu verarbeiten `<Party><PartyFavor/></Party>`, der XAML-Schemakontext muss in der Lage, den Namen und Typ des bestimmen die `ContentProperty` von `Party`, und daher auch müssen wissen, für die XAML-Namespaceinformationen `Party` und `PartyFavor`. Bei der Standard-XAML-Schemakontext meldet der statische Reflektion ein Großteil der XAML-Typsysteminformationen, der zum Generieren von XAML-Typknoten im Knotenstream erforderlich ist.  
  
 Um ein Objektdiagramm aus einem XAML-Knotenstream zu generieren, müssen der XAML-Namespace-Deklarationen für jedes XAML-Präfix in das ursprüngliche Markup verwendet, und klicken Sie in der XAML-Knotenstream aufgezeichnet vorhanden sein. An diesem Punkt Instanzen erstellt werden, und "true" verhält sich Typzuordnung.  
  
 Bei Bedarf mit XAML-Namespaceinformationen, in Fällen, vorab aufgefüllt wird, in dem der XAML-Namespace den XAML-Schemakontext verwendet werden sollen im Markup nicht definiert ist, ist eine Technik Sie können zum Deklarieren von XML-Namespace-Deklarationen in der <xref:System.Xml.XmlParserContext> für eine <xref:System.Xml.XmlReader>. Klicken Sie dann verwenden, die <xref:System.Xml.XmlReader> als Eingabe für einen XAML-Reader-Konstruktor oder <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Zwei andere API, die für XAML-Namespace in .NET Framework-XAML-Dienste verarbeiten relevant sind, sind die Attribute <xref:System.Windows.Markup.XmlnsDefinitionAttribute> und <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Diese Attribute gelten für Assemblys. <xref:System.Windows.Markup.XmlnsDefinitionAttribute> wird von einem XAML-Schemakontext verwendet, um alle XAML-Namespacedeklaration zu interpretieren, die einen URI enthält. <xref:System.Windows.Markup.XmlnsPrefixAttribute> wird von Tools verwendet, die XAML ausgeben, damit Sie ein bestimmter XAML-Namespace mit einem vorhersagbaren Präfix serialisiert werden kann. Weitere Informationen finden Sie unter [XAML-Related CLR-Attribute für benutzerdefinierte Typen und Bibliotheken](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Siehe auch

- [Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten](understanding-xaml-node-stream-structures-and-concepts.md)
