---
title: "XAML Namespaces for .NET Framework XAML Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# XAML Namespaces for .NET Framework XAML Services
Ein XAML\-Namespace ist ein Konzept, das die Definition eines XML\-Namespace erweitert.  Wie bei einem XML\-Namespace können Sie einen XAML\-Namespace mit einem `xmlns`\-Attribut im Markup definieren.  XAML\-Namespaces werden auch im XAML\-Knotenstream und anderen XAML\-Dienst\-APIs dargestellt.  In diesem Thema wird das Konzept des XAML\-Namespace erörtert, und es wird beschrieben, wie XAML\-Namespaces definiert und von XAML\-Schemakontexten und anderen Aspekten von .NET Framework\-XAML\-Diensten verwendet werden.  
  
## XML\-Namespace und XAML\-Namespace  
 So wie XAML eine spezielle Form von XML ist, ist ein XAML\-Namespace ein spezialisierter XML\-Namespace, der die grundlegende XML\-Form für das Markup verwendet.  Im Markup deklarieren Sie einen XAML\-Namespace und seine Zuordnung mithilfe eines `xmlns`\-Attributs, das auf ein Element angewendet wird.  Die `xmlns`\-Deklaration kann für das gleiche Element vorgenommen werden, in dem der XAML\-Namespace deklariert ist.  Eine XAML\-Namespacedeklaration für ein Element gilt für dieses Element, alle Attribute des Elements und alle untergeordneten Elemente des Elements.  Für Attribute kann ein XAML\-Namespace verwendet werden, der nicht mit dem des Elements identisch ist, in dem das Attribut enthalten ist, solange der Attributname selbst im Markup auf das Präfix verweist.  
  
 Der Unterschied zwischen einem XAML\-Namespace und einem XML\-Namespace besteht darin, dass ein XML\-Namespace verwendet werden kann, um auf ein Schema zu verweisen oder um einfach Entitäten zu unterscheiden.  Bei XAML müssen die in XAML verwendeten Typen und Member letztlich in Unterstützungstypen aufgelöst werden, und XML\-Schemakonzepte sind nicht gut für diese Funktion geeignet.  Der XAML\-Namespace enthält Informationen, die für den XAML\-Schemakontext verfügbar sein müssen, damit er diese Typzuordnung vornehmen kann.  
  
## XAML\-Namespacekomponenten  
 Die Definition des XAML\-Namespace besteht aus zwei Komponenten: einem Präfix und einem Bezeichner.  Jede dieser Komponenten ist vorhanden, wenn ein XAML\-Namespace im Markup deklariert oder im XAML\-Typsystem definiert wird.  
  
 Das Präfix kann eine beliebige Zeichenfolge gemäß der [W3C Namespaces in XML 1.0\-Spezifikation](http://go.microsoft.com/fwlink/?LinkID=161735) \(möglicherweise in englischer Sprache\) sein.  Gemäß der Konvention sind die Präfixe in der Regel sehr kurze Zeichenfolgen, da das Präfix in einer typischen Markupdatei oft wiederholt wird.  Für bestimmte XAML\-Namespaces, die in mehreren XAML\-Implementierungen verwendet werden sollen, werden bestimmte konventionelle Präfixe verwendet.  Der XAML\-Namespace der XAML\-Sprache wird z. B. normalerweise mit dem Präfix `x` zugeordnet.  Sie können einen XAML\-Standardnamespace definieren, in dem das Präfix nicht in der Definition angegeben ist, sondern als leere Zeichenfolge dargestellt wird, wenn es von einer .NET\-Framework\-XAML\-Dienst\-API definiert oder abgefragt wird.  In der Regel wird der XAML\-Standardnamespace so ausgewählt, dass in einer XAML\-Implementierungstechnologie und den zugehörigen Szenarien und Vokabularen möglichst viel Markup verwendet werden kann, in dem das Präfix weglassen wird.  
  
 Der Bezeichner kann eine beliebige Zeichenfolge gemäß der [W3C Namespaces in XML 1.0\-Spezifikation](http://go.microsoft.com/fwlink/?LinkID=161735) \(möglicherweise in englischer Sprache\) sein.  Gemäß der Konvention werden Bezeichner für XML\-Namespaces oder XAML\-Namespaces häufig in URI\-Form angegeben, normalerweise als mittels Protokoll qualifizierter absoluter URI.  Häufig werden Versionsinformationen, die ein bestimmtes XAML\-Vokabular definieren, als Teil der Pfadzeichenfolge impliziert.  Für XAML\-Namespaces gilt zusätzlich zur XML\-URI\-Konvention eine weitere Bezeichnerkonvention.  Bei XAML\-Namespaces enthält der Bezeichner Informationen, die von einem XAML\-Schemakontext benötigt werden, um die als Elemente in diesem XAML\-Namespace angegebenen Typen aufzulösen oder um Attribute in Member aufzulösen.  
  
 Zur Übermittlung dieser Informationen an einen XAML\-Schemakontext kann der Bezeichner für einen XAML\-Namespace dennoch in URI\-Form vorliegen.  In diesem Fall wird der URI jedoch auch als übereinstimmender Bezeichner in einer bestimmten Assembly oder einer Liste von Assemblys deklariert.  Zu diesem Zweck wird der Assembly <xref:System.Windows.Markup.XmlnsDefinitionAttribute> zugeordnet.  Diese Methode zur Identifizierung des XAML\-Namespace und Unterstützung eines CLR\-basierten Typauflösungsverhaltens in der zugeordneten Assembly wird vom XAML\-Standardschemakontext in .NET Framework\-XAML\-Diensten unterstützt.  Im Allgemeinen kann diese Konvention für Fälle verwendet, in denen der XAML\-Schemakontext die CLR beinhaltet oder auf dem XAML\-Standardschemakontext basiert, der zum Lesen von CLR\-Attributen aus CLR\-Assemblys erforderlich ist.  
  
 XAML\-Namespaces können auch anhand einer Konvention identifiziert werden, bei der ein CLR\-Namespace und eine Assembly mit Typdefinition bereitgestellt werden.  Diese Konvention wird in Fällen verwendet, in denen keine <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Zuordnung in den Assemblys vorhanden ist, die Typen enthalten.  Diese Konvention ist möglicherweise komplexer als die URI\-Konvention und kann zudem zu Mehrdeutigkeiten und Duplikaten führen, da auf unterschiedliche Weise auf eine Assembly verwiesen werden kann.  
  
 Die einfachste Form eines Bezeichners nach der CLR\-Namespace\- und Assemblykonvention lautet wie folgt:  
  
 `clr-namespace:` *CLRNamespacename* `; assembly=` *Assemblykurzame*  
  
 `clr-namespace:` und `; assembly=` sind literale Komponenten der Syntax.  
  
 *CLRNamespacename* ist der Zeichenfolgenname, der einen CLR\-Namespace identifiziert.  Dieser Zeichenfolgenname enthält alle internen Punktzeichen \(.\), die Hinweise auf den CLR\-Namespace und seine Beziehung zu anderen CLR\-Namespaces liefern.  
  
 *Assemblykurzame* ist der Zeichenfolgenname einer Assembly, die in XAML nützliche Typen definiert.  Die Typen, auf die durch den deklarierten XAML\-Namespace zugegriffen wird, müssen in der Assembly definiert und mit *CLRNamespacename* ausdrücklich im CLR\-Namespace deklariert sein.  Der Zeichenfolgenname entspricht normalerweise den von <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=fullName> angegebenen Informationen.  
  
 Eine vollständigere Definition der CLR\-Namespace\- und Assemblykonvention lautet wie folgt:  
  
 `clr-namespace:` *CLRNamespacename* `; assembly=` *Assemblyname*  
  
 *Assemblyname* stellt eine beliebige Zeichenfolge dar, die als <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>\-Eingabe gültig ist.  Diese Zeichenfolge kann die Kultur, den öffentlichen Schlüssel oder Versionsinformationen enthalten \(Definitionen dieser Begriffe finden Sie im Referenzthema für <xref:System.Reflection.Assembly>\).  Das COFF\-Format und der Beweis \(die bei anderen Überladungen von <xref:System.Reflection.Assembly.Load%2A> verwendet werden\) sind beim Laden von XAML\-Assemblys nicht relevant. Alle Informationen müssen als Zeichenfolge dargestellt werden.  
  
 Die Angabe eines öffentlichen Schlüssels für die Assembly ist eine nützliche Technik im Hinblick auf die XAML\-Sicherheit oder die Beseitigung möglicher Mehrdeutigkeiten, die entstehen können, wenn Assemblys anhand des einfachen Namens geladen werden oder vorab in einem Cache oder einer Anwendungsdomäne vorhanden sind.  Weitere Informationen finden Sie unter [XAML Security Considerations](../../../docs/framework/xaml-services/xaml-security-considerations.md).  
  
## XAML\-Namespacedeklarationen in der XAML\-Dienst\-API  
 In der XAML\-Dienst\-API wird eine XAML\-Namespacedeklaration durch ein <xref:System.Xaml.NamespaceDeclaration>\-Objekt dargestellt.  Wenn Sie einen XAML\-Namespace im Code deklarieren, rufen Sie den <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29>\-Konstruktor auf.  Die Parameter `prefix` und `ns` werden als Zeichenfolgen angegeben. Die Eingabe zum Bereitstellen dieser Parameter entspricht der weiter oben in diesem Thema erläuterten Definition des XAML\-Namespacebezeichners und XAML\-Namespacepräfixes.  
  
 Wenn Sie die XAML\-Namespaceinformationen in einem XAML\-Knotenstream oder durch anderweitigen Zugriff auf das XAML\-Typsystem untersuchen, gibt <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=fullName> den XAML\-Namespacebezeichner an und <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=fullName> das XAML\-Namespacepräfix.  
  
 In einem XAML\-Knotenstream können die XAML\-Namespaceinformationen als XAML\-Knoten vor der jeweiligen Entität angezeigt werden.  Dies gilt auch für Fälle, in denen die XAML\-Namespaceinformationen vor dem `StartObject` des XAML\-Stammelements stehen.  Weitere Informationen finden Sie unter [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Bei vielen Szenarien mit der .NET Framework\-XAML\-Dienst\-API muss mindestens eine XAML\-Namespacedeklaration vorhanden sein, und die Deklaration muss die für einen XAML\-Schemakontext erforderlichen Informationen enthalten oder auf diese Informationen verweisen.  Die XAML\-Namespaces müssen entweder die zu ladenden Assemblys angeben oder die Auflösung bestimmter Typen in Namespaces und Assemblys unterstützen, die bereits geladen oder dem XAML\-Schemakontext bekannt sind.  
  
 Um einen XAML\-Knotenstream zu generieren, müssen XAML\-Typinformationen durch den XAML\-Schemakontext verfügbar sein.  Die XAML\-Typinformationen können nicht bestimmt werden, ohne zuvor den relevanten XAML\-Namespace für jeden zu erstellenden Knoten zu ermitteln.  An diesem Punkt werden noch keine Instanzen von Typen erstellt, der XAML\-Schemakontext muss jedoch möglicherweise nach Informationen aus der definierenden Assembly und dem Unterstützungstyp suchen.  Zum Verarbeiten des `<Party><PartyFavor/></Party>`\-Markup muss der XAML\-Schemakontext z. B. in der Lage sein, den Namen und Typ der `ContentProperty` von `Party` zu ermitteln. Daher müssen ihm auch die XAML\-Namespaceinformationen für `Party` und `PartyFavor` bekannt sein.  Im Fall des XAML\-Standardschemakontexts wird durch statische Reflektion ein Großteil der XAML\-Typsysteminformationen bereitgestellt, die zum Generieren von XAML\-Typknoten im Knotenstream erforderlich sind.  
  
 Um ein Objektdiagramm aus einem XAML\-Knotenstream zu generieren, müssen XAML\-Namespacedeklarationen für jedes im ursprünglichen Markup verwendete XAML\-Präfix vorhanden sein und im XAML\-Knotenstream aufgezeichnet werden.  An diesem Punkt werden Instanzen erstellt, und das eigentliche Typzuordnungsverhalten tritt auf.  
  
 Wenn Sie XAML\-Namespaceinformationen vorab auffüllen müssen \(in Fällen, in denen der vom XAML\-Schemakontext zu verwendende XAML\-Namespace nicht im Markup definiert ist\), können Sie XML\-Namespacedeklarationen im <xref:System.Xml.XmlParserContext> für einen <xref:System.Xml.XmlReader> deklarieren.  Anschließend verwenden Sie diesen <xref:System.Xml.XmlReader> als Eingabe für einen XAML\-Readerkonstruktor oder <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=fullName>.  
  
 Zwei weitere APIs, die für die XAML\-Namespacebehandlung in .NET Framework\-XAML\-Diensten relevant sind, sind die Attribute <xref:System.Windows.Markup.XmlnsDefinitionAttribute> und <xref:System.Windows.Markup.XmlnsPrefixAttribute>.  Diese Attribute gelten für Assemblys.  <xref:System.Windows.Markup.XmlnsDefinitionAttribute> wird von einem XAML\-Schemakontext verwendet, um eine XAML\-Namespacedeklaration zu interpretieren, die einen URI enthält.  <xref:System.Windows.Markup.XmlnsPrefixAttribute> wird von Tools verwendet, die XAML ausgeben, damit ein bestimmter XAML\-Namespace mit einem vorhersagbaren Präfix serialisiert werden kann.  Weitere Informationen finden Sie unter [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## Siehe auch  
 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)