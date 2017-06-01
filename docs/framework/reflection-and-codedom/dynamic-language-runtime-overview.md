---
title: "&#220;bersicht &#252;ber die Dynamic Language Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DLR"
  - "Dynamic Language Runtime"
  - "IronPython"
  - "IronRuby"
ms.assetid: f769a271-8aff-4bea-bfab-6160217ce23d
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# &#220;bersicht &#252;ber die Dynamic Language Runtime
Die *Dynamic Language Runtime* \(DLR\) ist eine Laufzeitumgebung, mit der der Common Language Runtime \(CLR\) eine Reihe von Diensten für dynamische Sprachen hinzugefügt wird.  Die DLR erleichtert die Entwicklung dynamischer Sprachen für die Ausführung in .NET Framework und das Hinzufügen dynamischer Funktionen zu statisch typisierten Sprachen.  
  
 Dynamische Sprachen können zur Laufzeit den Typ eines Objekts identifizieren, hingegen müssen Sie in statisch typisierten Sprachen, z. B. C\# und Visual Basic \(wenn Sie `Option Explicit On` verwenden\), Objekttypen zur Entwurfszeit angeben.  Beispiele für dynamische Sprachen sind Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra und Groovy.  
  
 Die meisten dynamischen Sprachen bieten Entwicklern folgende Vorteile:  
  
-   Die Möglichkeit, Feedbackschleifen, auch als Read\-Evaluate\-Print\-Schleifen \(REPL\) bezeichnet, zu verwenden.  Auf diese Weise können Sie mehrere Anweisungen eingeben und sofort ausführen, um die Ergebnisse anzuzeigen.  
  
-   Unterstützung für Top\-Down\-Entwicklung und auch die herkömmlichere Bottom\-Up\-Entwicklung.  Wenn Sie eine Top\-Down\-Methode verwenden, können Sie z. B. Funktionen aufrufen, die noch nicht implementiert wurden, und dann bei Bedarf zugrunde liegende Implementierungen hinzufügen.  
  
-   Einfachere Umgestaltungen und Codeänderungen, da Sie statische Typdeklarationen nicht im gesamten Code ändern müssen.  
  
 Dynamische Sprachen bilden ausgezeichnete Skriptsprachen.  Mit neuen Befehlen und Funktionen können Kunden Anwendungen leicht erweitern, die in dynamischen Sprachen erstellt wurden.  Dynamische Sprachen werden häufig auch zum Erstellen von Websites und Testumgebungen, Verwalten von Serverfarmen, Entwickeln verschiedener Dienstprogramme und Ausführen von Datentransformationen verwendet.  
  
 Der Zweck der DLR besteht darin, die Ausführung eines Systems von dynamischen Sprachen in .NET Framework und dessen Interoperabilität mit .NET zu ermöglichen.  Die DLR führt in Visual Studio 2010 dynamische Objekte für C\# und Visual Basic ein, um dynamisches Verhalten in diesen Sprachen zu unterstützen und deren Interoperation mit dynamischen Sprachen zu ermöglichen.  
  
 Die DLR erleichtert zudem das Erstellen von Bibliotheken, die dynamische Vorgänge unterstützen.  Bei einer Bibliothek, für die XML\- oder JSON\-Objekte \(JavaScript Objekt Notation\) verwendet werden, können diese in Sprachen, für die die DLR verwendet wird, als dynamische Objekte angezeigt werden.  So können die Benutzer der Bibliothek syntaktisch einfacheren und natürlicheren Code für Objekte und den Zugriff auf Objektmember schreiben.  
  
 Beispielsweise können Sie mit dem folgenden Code einen XML\-Indikator in C\# inkrementieren.  
  
 `Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);`  
  
 Mit der DLR können Sie für denselben Vorgang stattdessen den folgenden Code verwenden.  
  
 `scriptobj.Count += 1;`  
  
 Wie die CLR ist die DLR Teil von .NET Framework und wird mit den Installationspaketen für .NET Framework und Visual Studio ausgeliefert.  Die Open Source\-Version der DLR steht auch auf der [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) Website heruntergeladen.  
  
> [!NOTE]
>  Die Open Source\-Version der DLR enthält sämtliche Funktionen der DLR in Visual Studio und .NET Framework.  Zudem bietet sie zusätzliche Unterstützung für Sprachimplementierer.  Weitere Informationen finden Sie in der [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) Dokumentation auf der Website.  
  
 Einige Beispiele für Sprachen, die mit der DLR entwickelt wurden:  
  
-   IronPython.  Open Source\-Software auf der [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141040) Website.  
  
-   IronRuby.  Open Source\-Software auf der [RubyForge](http://go.microsoft.com/fwlink/?LinkId=141044) Website.  
  
## Wesentliche Vorteile der DLR  
 Die DLR bietet die folgenden Vorteile.  
  
### Vereinfachte Portierung dynamischer Sprachen nach .NET Framework  
 Mit der DLR müssen Sprachimplementierer lexikalische Analyzer, Parser, semantische Analyzer, Codegeneratoren und andere Tools nicht mehr selbst erstellen.  Zur Verwendung der DLR muss eine Sprache *Ausdrucksbaumstrukturen* erzeugen, die Code auf Sprachenebene in einer baumförmigen Struktur darstellen, sowie Laufzeithilfsroutinen und optionale dynamische Objekte erzeugen, die die <xref:System.Dynamic.IDynamicMetaObjectProvider>\-Schnittstelle implementieren.  Mit der DLR und .NET Framework wird ein großer Teil der Codeanalyse und der Codegenerierungsaufgaben automatisiert.  Damit können sich Sprachimplementierer auf eindeutige Sprachfunktionen konzentrieren.  
  
### Verwendung dynamischer Funktionen in statisch typisierten Sprachen  
 In vorhandenen .NET Framework\-Sprachen, z. B. C\# und Visual Basic, können dynamische Objekte erstellt und zusammen mit statisch typisierten Objekten verwendet werden.  In C\# und Visual Basic können beispielsweise dynamische Objekte für die HTML\-, DOM\- \(Document Object Model, Dokumentobjektmodell\) und .NET\-Reflektion verwendet werden.  
  
### Zukünftige Vorteile der DLR und von .NET Framework  
 Mit der DLR implementierte Sprachen können von den Vorteilen zukünftiger DLR\- und .NET Framework\-Verbesserungen profitieren.  Wenn beispielsweise eine neue Version von .NET Framework mit einem verbesserten Garbage Collector oder einer schnelleren Assemblyladezeit veröffentlicht wird, wirkt sich dieser Vorteil sofort auch auf mit der DLR implementierte Sprachen aus.  Wenn der DLR Optimierungen hinzugefügt werden, z. B. eine bessere Kompilierung, verbessert sich auch die Leistung aller mit der DLR implementierten Sprachen.  
  
### Freigabe von Bibliotheken und Objekten  
 Die in einer Sprache implementierten Objekte und die Bibliotheken können auch von anderen Sprachen verwendet werden.  Die DLR ermöglicht zudem die Interoperation zwischen statisch typisierten und dynamischen Sprachen.  Beispielsweise kann in C\# ein dynamisches Objekt deklariert werden, das eine in einer dynamischen Sprache geschriebene Bibliothek verwendet.  Gleichzeitig können in dynamischen Sprachen Bibliotheken von .NET Framework verwendet werden.  
  
### Schneller dynamischer Dispatch und Aufruf  
 Die DLR bietet eine schnelle Ausführung dynamischer Vorgänge durch Unterstützung erweiterter polymorpher Zwischenspeicherung.  Die DLR erstellt Regeln, anhand derer Vorgänge mit Objekten an die erforderlichen Laufzeitimplementierungen gebunden werden, und speichert diese Regeln dann im Cache, um während aufeinander folgender Ausführungen desselben Codes für gleiche Objekttypen ressourcenintensive Bindungsberechnungen zu vermeiden.  
  
## DLR\-Architektur  
 Die folgende Abbildung zeigt die Architektur der Dynamic Language Runtime.  
  
 ![Übersicht über die DLR&#45;Architektur &#40;Dynamic Language Runtime&#41;](../../../docs/framework/reflection-and-codedom/media/dlr-archoverview.png "DLR\_ArchOverview")  
DLR\-Architektur  
  
 Die DLR fügt der CLR eine Reihe von Diensten zur besseren Unterstützung dynamischer Sprachen hinzu.  Zu diesen Diensten gehören die folgenden:  
  
-   Ausdrucksbaumstrukturen.  Die DLR stellt mithilfe von Ausdrucksbaumstrukturen die Sprachsemantik dar.  Zu diesem Zweck umfasst die DLR erweiterte LINQ\-Ausdrucksbaumstrukturen mit Ablaufsteuerungs\-, Zuweisungs\- und anderen Sprachmodellierungsknoten.  Weitere Informationen finden Sie unter [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   Zwischenspeicherung von Aufrufsites.  Als *dynamische Aufrufsite* wird eine Stelle im Code bezeichnet, an der Sie bestimmte Operationen für dynamische Objekte ausführen können, z. B. `a + b` oder `a.b()`.  Die DLR speichert die Merkmale von `a` und `b` \(meist die Typen dieser Objekte\) und Informationen zur Operation im Cache.  Wenn eine solche Operation bereits zuvor ausgeführt wurde, ruft die DLR alle erforderlichen Informationen aus dem Cache ab, um einen schnellen Dispatch zu gewährleisten.  
  
-   Interoperabilität dynamischer Objekte.  Die DLR stellt eine Reihe von Klassen und Schnittstellen bereit, die dynamische Objekte und Operationen darstellen und von Sprachimplementierern und Autoren dynamischer Bibliotheken verwendet werden können.  Zu diesen Klassen und Schnittstellen zählen u. a. <xref:System.Dynamic.IDynamicMetaObjectProvider>, <xref:System.Dynamic.DynamicMetaObject>, <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject>.  
  
 Die DLR kommuniziert mit Bindern in Aufrufsites nicht nur mit .NET Framework, sondern auch mit anderen Infrastrukturen und Diensten, u. a. Silverlight und COM.  Binder kapseln die Semantik einer Sprache und geben an, wie Operationen in einer Aufrufsite mithilfe von Ausdrucksbaumstrukturen ausgeführt werden sollen.  So können dynamische und statisch typisierte Sprachen, die die DLR verwenden, Bibliotheken gemeinsam nutzen und auf alle von der DLR unterstützten Technologien zugreifen.  
  
## DLR\-Dokumentation  
 Weitere Informationen darüber, wie die Open Source\-Version der DLR verwendet, um dynamisches Verhalten einer Sprache hinzuzufügen oder dazu, wie der Verwendung einer dynamischen Sprache in .NET Framework, finden Sie in der [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) Dokumentation auf der Website aktiviert.  
  
## Siehe auch  
 <xref:System.Dynamic.ExpandoObject>   
 <xref:System.Dynamic.DynamicObject>   
 [Common Language Runtime](../../../docs/standard/clr.md)   
 [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../Topic/Walkthrough:%20Creating%20and%20Using%20Dynamic%20Objects%20\(C%23%20and%20Visual%20Basic\).md)