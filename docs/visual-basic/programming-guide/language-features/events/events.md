---
title: "Events (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "events [Visual Basic], about events"
  - "events [Visual Basic]"
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Events (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Sie können sich ein [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)]\-Projekt als eine Reihe von Prozeduren vorstellen, die nacheinander ausgeführt werden, doch sind die meisten Programme tatsächlich ereignisgesteuert. Das bedeutet, dass der Ausführungsablauf von externen Vorkommnissen bestimmt wird, die als *Ereignisse* bezeichnet werden.  
  
 Ein Ereignis ist ein Signal, das eine Anwendung darüber informiert, dass etwas Wichtiges geschehen ist.  Wenn der Benutzer beispielsweise auf ein Steuerelement in einem Formular klickt, löst das Formular ein `Click`\-Ereignis aus und ruft eine Prozedur auf, die das Ereignis behandelt.  Darüber hinaus ermöglichen Ereignisse die Kommunikation zwischen separaten Aufgaben.  Beispiel: Die Anwendung führt separat von der Hauptanwendung eine Sortieraufgabe aus.  Wenn ein Benutzer den Sortiervorgang abbricht, kann die Anwendung ein Cancel\-Ereignis senden, das den Abbruch des Sortiervorgangs veranlasst.  
  
## Begriffe und Konzepte im Zusammenhang mit Ereignissen  
 In diesem Abschnitt werden die in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] im Zusammenhang mit Ereignissen verwendeten Begriffe und Konzepte erläutert.  
  
### Deklarieren von Ereignissen  
 Ereignisse werden innerhalb von Klassen, Strukturen, Modulen und Schnittstellen mithilfe des `Event`\-Schlüsselworts deklariert, wie im folgenden Beispiel dargestellt:  
  
 [!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#24)]  
  
### Auslösen von Ereignissen  
 Ein Ereignis ist mit einer Nachricht vergleichbar, die bekannt gibt, dass etwas Wichtiges geschehen ist.  Das Senden der Nachricht wird als *Auslösen* des Ereignisses bezeichnet.  In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] lösen Sie Ereignisse mit der `RaiseEvent`\-Anweisung aus, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#25)]  
  
 Ereignisse müssen im Gültigkeitsbereich der Klasse, des Moduls oder der Struktur ausgelöst werden, in der sie deklariert wurden.  So kann beispielsweise eine abgeleitete Klasse keine Ereignisse auslösen, die von einer Basisklasse geerbt wurden.  
  
### Ereignissender  
 Jedes Objekt, das in der Lage ist, ein Ereignis auszulösen, ist ein *Ereignissender* \(auch *Ereignisquelle* genannt\).  Formulare, Steuerelemente und benutzerdefinierte Objekte sind Beispiele für Ereignissender.  
  
### Ereignishandler  
 *Ereignishandler* sind Prozeduren, die aufgerufen werden, wenn ein entsprechendes Ereignis auftritt.  Als Ereignishandler kann jede gültige Unterroutine mit einer übereinstimmenden Signatur verwendet werden.  Funktionen können nicht als Ereignishandler verwendet werden, da sie keinen Wert an die Ereignisquelle zurückgeben können.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verwendet eine standardmäßige Benennungskonvention für Ereignishandler. Danach besteht der Name aus dem Namen des Ereignissenders, einem Unterstrich und dem Namen des Ereignisses.  Das `Click`\-Ereignis einer Schaltfläche mit dem Namen `button1` heißt beispielsweise `Sub button1_Click`.  
  
> [!NOTE]
>  Die Verwendung dieser Benennungskonvention wird für die Definition von Ereignishandlern für eigene Ereignisse empfohlen, ist jedoch nicht erforderlich. Sie können stattdessen auch einen gültigen Unterroutinennamen verwenden.  
  
## Verknüpfen von Ereignissen mit Ereignishandlern  
 Bevor ein Ereignishandler verwendet werden kann, müssen sie ihn über die `Handles`\-Anweisung oder die `AddHandler`\-Anweisung mit einem Ereignis verknüpfen.  
  
### WithEvents und die Handles\-Klausel  
 Die `WithEvents`\-Anweisung und die `Handles`\-Klausel bieten die Möglichkeit, Ereignishandler per Deklaration festzulegen.  Ein Ereignis, das durch ein Objekt ausgelöst wird, das mit dem `WithEvents`\-Schlüsselwort deklariert wurde, kann von einer beliebigen Prozedur mit einer `Handles`\-Anweisung für dieses Ereignis behandelt werden \(siehe folgendes Beispiel\):  
  
 [!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#1)]  
  
 Die `WithEvents`\-Anweisung und die `Handles`\-Klausel sind häufig die beste Kombination für Ereignishandler, da die hier verwendete Deklarationssyntax das Kodieren, Lesen und Debuggen der Ereignisbehandlung vereinfacht.  Beachten Sie jedoch die folgenden Beschränkungen bei der Verwendung von `WithEvents`\-Variablen:  
  
-   Sie können eine `WithEvents`\-Variable nicht als Objektvariable verwenden.  Dies bedeutet, Sie können die Variable nicht als `Object` deklarieren, sondern Sie müssen den Klassennamen angeben, wenn Sie die Variable deklarieren.  
  
-   Da freigegebene Ereignisse `` nicht an Klasseninstanzen gebunden sind, können Sie `WithEvents` nicht für die deklarative Behandlung freigegebener Ereignisse verwenden.  Ebenso können Sie `WithEvents` oder `Handles` nicht zum Behandeln von Ereignissen aus einer `Structure` verwenden.  In beiden Fällen können Sie diese Ereignisse mit der `AddHandler`\-Anweisung behandeln.  
  
-   Sie können keine Arrays aus `WithEvents`\-Variablen erstellen.  
  
 Mit `WithEvents`\-Variablen kann ein einziger Ereignishandler eine oder mehrere Ereignisarten bzw. einen oder mehrere Ereignishandler zur Behandlung derselben Art von Ereignissen behandeln.  
  
 Die `Handles`\-Klausel ist zwar das Standardverfahren zum Verknüpfen eines Ereignisses mit einem Ereignishandler, ist jedoch dennoch auf das Verknüpfen von Ereignissen mit Ereignishandlern während der Kompilierung beschränkt.  
  
 In einigen Fällen, z. B. bei Ereignissen, die Formularen oder Steuerelementen zugeordnet sind, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] automatisch einen Stub für einen leeren Ereignishandler und ordnet ihn einem Ereignis zu.  Wenn Sie z. B. im Entwurfsmodus auf eine Befehlsschaltfläche doppelklicken, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] einen leeren Ereignishandler und eine `WithEvents`\-Variable für die Befehlsschaltfläche \(siehe folgenden Code\):  
  
 [!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#26)]  
  
### "AddHandler" und "RemoveHandler"  
 Die `AddHandler`\-Anweisung ähnelt der `Handles`\-Klausel insofern, als Sie mit beiden einen Ereignishandler angeben können.  `AddHandler` bietet Ihnen jedoch zusammen mit `RemoveHandler` mehr Flexibilität als die `Handles`\-Klausel, da es ein dynamisches Hinzufügen, Entfernen und Ändern des einem Ereignis zugeordneten Ereignishandlers ermöglicht.  Wenn Sie freigegebene Ereignisse oder Ereignisse aus einer Struktur behandeln möchten, müssen Sie `AddHandler` verwenden.  
  
 `AddHandler` benötigt zwei Argumente: den Namen eines Ereignisses von einem Ereignissender \(z. B. einem Steuerelement\) und einen Ausdruck, der einen Delegaten ergibt.  Wenn Sie `AddHandler` verwenden, müssen Sie die Delegatklasse nicht explizit angeben, da die `AddressOf`\-Anweisung stets einen Verweis auf den Delegaten zurückgibt.  Im folgenden Beispiel wird ein Ereignishandler mit einem Ereignis verknüpft, das durch ein Objekt ausgelöst wird:  
  
 [!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#28)]  
  
 Für `RemoveHandler`, der ein Ereignis von einem Ereignishandler trennt, wird die gleiche Syntax verwendet wie für `AddHandler`.  Beispiele:  
  
 [!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#29)]  
  
 Im folgenden Beispiel ist einem Ereignis ein Ereignishandler zugeordnet, und das Ereignis wird ausgelöst.  Der Ereignishandler fängt das Ereignis ab und zeigt eine Meldung an.  
  
 Anschließend wird der erste Ereignishandler entfernt, und dem Ereignis wird ein anderer Ereignishandler zugeordnet.  Beim erneuten Auslösen des Ereignisses wird eine andere Meldung angezeigt.  
  
 Schließlich wird der zweite Ereignishandler entfernt, und das Ereignis wird zum dritten Mal ausgelöst.  Da dem Ereignis kein Ereignishandler mehr zugeordnet ist, wird keine Aktion ausgeführt.  
  
 [!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class2.vb#38)]  
  
## Behandeln von Ereignissen, die aus einer Basisklasse geerbt wurden  
 *Abgeleitete Klassen* sind Klassen, die Merkmale von einer Basisklasse erben. Sie können mithilfe der `Handles` `MyBase`\-Anweisung Ereignisse behandeln, die von ihrer Basisklasse ausgelöst wurden.  
  
#### So behandeln Sie Ereignisse aus einer Basisklasse  
  
-   Deklarieren Sie einen Ereignishandler in der abgeleiteten Klasse, indem Sie der Deklarationszeile der Prozedur für den Ereignishandler eine `Handles MyBase.`*Ereignisname*\-Anweisung hinzufügen. Dabei ist *Ereignisname* der Name des zu behandelnden Ereignisses in der Basisklasse.  Beispiele:  
  
     [!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#12)]  
  
## Verwandte Abschnitte  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|Stellt eine schrittweise Beschreibung des Deklarierens und Auslösens von Ereignissen für eine Klasse bereit.|  
|[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|Veranschaulicht das Schreiben einer Ereignishandlerprozedur.|  
|[How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|Veranschaulicht, wie ein benutzerdefiniertes Ereignis definiert wird, das den asynchronen Aufruf seiner Ereignishandler zulässt.|  
|[How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|Veranschaulicht, wie ein benutzerdefiniertes Ereignis definiert wird, das nur bei der Behandlung des Ereignisses Speicher nutzt.|  
|[Troubleshooting Inherited Event Handlers in Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|Listet allgemeine Probleme auf, die bei Ereignishandlern in geerbten Komponenten auftreten können.|  
|[Ereignisse](../Topic/Handling%20and%20Raising%20Events.md)|Bietet eine Übersicht über das Ereignismodell in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)].|  
|[Erstellen von Ereignishandlern in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)|Beschreibt die Verwendung von Ereignissen, die Windows Forms\-Objekten zugeordnet sind.|  
|[Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)|Stellt eine Übersicht über Delegaten in Visual Basic bereit.|