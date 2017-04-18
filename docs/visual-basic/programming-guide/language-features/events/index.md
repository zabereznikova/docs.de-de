---
title: Ereignisse (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 625f4b24dde4200187e1339983d89b9ce92609c9
ms.lasthandoff: 03/13/2017

---
# <a name="events-visual-basic"></a>Ereignisse (Visual Basic)
Sie können sich ein [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)]-Projekt als eine Reihe von Prozeduren vorstellen, die nacheinander ausgeführt werden, doch sind die meisten Programme tatsächlich ereignisgesteuert. Das bedeutet, dass der Ausführungsablauf von externen Vorkommnissen bestimmt wird, die als *Ereignisse* bezeichnet werden.  
  
 Ein Ereignis ist ein Signal, das eine Anwendung darüber informiert, dass etwas Wichtiges geschehen ist. Wenn ein Benutzer beispielsweise auf ein Steuerelement in einem Formular klickt, löst das Formular ein `Click`-Ereignis aus und ruft eine Prozedur auf, die das Ereignis behandelt. Ereignisse ermöglichen zudem die Kommunikation zwischen separaten Tasks. Beispiel: Die Anwendung führt separat von der Hauptanwendung einen Sortiertask aus. Wenn ein Benutzer den Sortiervorgang abbricht, kann die Anwendung ein Cancel-Ereignis senden, das den Abbruch des Sortiervorgangs veranlasst.  
  
## <a name="event-terms-and-concepts"></a>Ereignisse – Begriffe und Konzepte  
 In diesem Abschnitt werden die in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] im Zusammenhang mit Ereignissen verwendeten Begriffe und Konzepte erläutert.  
  
### <a name="declaring-events"></a>Deklarieren von Ereignissen  
 Ereignisse werden innerhalb von Klassen, Strukturen, Modulen und Schnittstellen mithilfe des `Event`-Schlüsselworts deklariert, wie im folgenden Beispiel dargestellt:  
  
 [!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]  
  
### <a name="raising-events"></a>Auslösen von Ereignissen  
 Ein Ereignis ist mit einer Nachricht vergleichbar, die bekannt gibt, dass etwas Wichtiges geschehen ist. Das Senden der Nachricht wird als *Auslösen* des Ereignisses bezeichnet. In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] lösen Sie Ereignisse mit der `RaiseEvent`-Anweisung aus, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]  
  
 Ereignisse müssen im Geltungsbereich der Klasse, des Moduls oder der Struktur ausgelöst werden, in der bzw. dem sie deklariert wurden. So kann beispielsweise eine abgeleitete Klasse keine Ereignisse auslösen, die von einer Basisklasse geerbt wurden.  
  
### <a name="event-senders"></a>Ereignissender  
 Jedes Objekt, das in der Lage ist, ein Ereignis auszulösen, ist ein *Ereignissender* (auch *Ereignisquelle* genannt). Formulare, Steuerelemente und benutzerdefinierte Objekte sind Beispiele für Ereignissender.  
  
### <a name="event-handlers"></a>Ereignishandler  
 *Ereignishandler* sind Prozeduren, die aufgerufen werden, wenn ein entsprechendes Ereignis eintritt. Jede gültige Unterroutine mit einer übereinstimmenden Signatur kann als Ereignishandler verwendet werden. Funktionen können jedoch nicht als Ereignishandler verwendet werden, da sie keinen Wert an die Ereignisquelle zurückgeben können.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verwendet eine standardmäßige Benennungskonvention für Ereignishandler, die den Namen des Ereignissenders, einen Unterstrich und dem Namen des Ereignisses kombiniert. Das `Click`-Ereignis einer Schaltfläche mit dem Namen `button1` heißt beispielsweise `Sub button1_Click`.  
  
> [!NOTE]
>  Beim Definieren von Ereignishandlern für Ihre Ereignisse empfiehlt sich die Verwendung dieser Benennungskonvention, sie ist jedoch nicht erforderlich. Sie können stattdessen auch jeden gültigen Unterroutinennamen verwenden.  
  
## <a name="associating-events-with-event-handlers"></a>Verknüpfen von Ereignissen mit Ereignishandlern  
 Bevor ein Ereignishandler verwendet werden kann, müssen Sie ihn über die `Handles`- oder die `AddHandler`-Anweisung mit einem Ereignis verknüpfen.  
  
### <a name="withevents-and-the-handles-clause"></a>WithEvents und die Handles-Klausel  
 Die `WithEvents`-Anweisung und die `Handles`-Klausel bieten die Möglichkeit, Ereignishandler per Deklaration festzulegen. Ein Ereignis, das durch ein mit dem `WithEvents`-Schlüsselwort deklariertes Objekt ausgelöst wird, kann von einer beliebigen Prozedur mit einer `Handles`-Anweisung für dieses Ereignis behandelt werden (siehe folgendes Beispiel):  
  
 [!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]  
  
 Die `WithEvents`-Anweisung und die `Handles`-Klausel sind häufig die beste Wahl für Ereignishandler, da die hier verwendete Deklarationssyntax das Programmieren, Lesen und Debuggen der Ereignisbehandlung vereinfacht. Beachten Sie jedoch die folgenden Einschränkungen bei der Verwendung von `WithEvents`-Variablen:  
  
-   Sie können eine `WithEvents`-Variable nicht als Objektvariable verwenden. Dies bedeutet, dass Sie die Variable nicht als `Object` deklarieren können, sondern den Klassennamen angeben müssen, wenn Sie die Variable deklarieren.  
  
-   Da freigegebene Ereignisse nicht an Klasseninstanzen gebunden sind, können Sie `WithEvents` nicht für die deklarative Behandlung freigegebener Ereignisse verwenden. Ebenso können Sie `WithEvents` oder `Handles` nicht zum Behandeln von Ereignissen aus einer `Structure` verwenden. In beiden Fällen können Sie diese Ereignisse mit der `AddHandler`-Anweisung behandeln.  
  
-   Sie können keine Arrays aus `WithEvents`-Variablen erstellen.  
  
 Mit `WithEvents`-Variablen kann ein einziger Ereignishandler eine oder mehrere Ereignisarten bzw. einen oder mehrere Ereignishandler zur Behandlung derselben Art von Ereignissen verarbeiten.  
  
 Die `Handles`-Klausel ist zwar das Standardverfahren zum Verknüpfen eines Ereignisses mit einem Ereignishandler, ist aber auf das Verknüpfen von Ereignissen mit Ereignishandlern zur Kompilierzeit beschränkt.  
  
 In einigen Fällen, z.B. bei Ereignissen, die Formularen oder Steuerelementen zugeordnet sind, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatisch einen Stub für einen leeren Ereignishandler und ordnet ihn einem Ereignis zu. Wenn Sie z.B. im Entwurfsmodus auf eine Befehlsschaltfläche doppelklicken, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen leeren Ereignishandler und eine `WithEvents`-Variable für die Befehlsschaltfläche, wie im folgenden Code veranschaulicht:  
  
 [!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]  
  
### <a name="addhandler-and-removehandler"></a>AddHandler und RemoveHandler  
 Die `AddHandler`-Anweisung ähnelt der `Handles`-Klausel insofern, als Sie mit beiden einen Ereignishandler angeben können. `AddHandler` bietet Ihnen jedoch zusammen mit `RemoveHandler` mehr Flexibilität als die `Handles`-Klausel, da es ein dynamisches Hinzufügen, Entfernen und Ändern des einem Ereignis zugeordneten Ereignishandlers ermöglicht. Wenn Sie freigegebene Ereignisse oder Ereignisse aus einer Struktur behandeln möchten, müssen Sie `AddHandler` verwenden.  
  
 `AddHandler` benötigt zwei Argumente: den Namen eines Ereignisses von einem Ereignissender (z.B. einem Steuerelement) und einen Ausdruck, der einen Delegaten ergibt. Wenn Sie `AddHandler` verwenden, müssen Sie die Delegatklasse nicht explizit angeben, da die `AddressOf`-Anweisung stets einen Verweis auf den Delegaten zurückgibt. Im folgenden Beispiel wird ein Ereignishandler mit einem Ereignis verknüpft, das durch ein Objekt ausgelöst wird:  
  
 [!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]  
  
 Für `RemoveHandler`, wodurch ein Ereignis von einem Ereignishandler getrennt wird, wird die gleiche Syntax verwendet wie für `AddHandler`. Zum Beispiel:  
  
 [!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]  
  
 Im folgenden Beispiel ist einem Ereignis ein Ereignishandler zugeordnet, und das Ereignis wird ausgelöst. Der Ereignishandler fängt das Ereignis ab und zeigt eine Meldung an.  
  
 Anschließend wird der erste Ereignishandler entfernt, und dem Ereignis wird ein anderer Ereignishandler zugeordnet. Beim erneuten Auslösen des Ereignisses wird eine andere Meldung angezeigt.  
  
 Schließlich wird der zweite Ereignishandler entfernt, und das Ereignis wird zum dritten Mal ausgelöst. Da dem Ereignis kein Ereignishandler mehr zugeordnet ist, wird keine Aktion ausgeführt.  
  
 [!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]  
  
## <a name="handling-events-inherited-from-a-base-class"></a>Behandeln von Ereignissen, die von einer Basisklasse geerbt wurden  
 *Abgeleitete Klassen* sind Klassen, die Merkmale von einer Basisklasse erben. Sie können mithilfe der `Handles``MyBase`-Anweisung Ereignisse behandeln, die von ihrer Basisklasse ausgelöst wurden.  
  
#### <a name="to-handle-events-from-a-base-class"></a>So behandeln Sie Ereignisse aus einer Basisklasse  
  
-   Deklarieren Sie einen Ereignishandler in der abgeleiteten Klasse, indem Sie der Deklarationszeile der Prozedur für den Ereignishandler eine `Handles MyBase.`*Ereignisname*-Anweisung hinzufügen. Dabei ist *Ereignisname* der Name des zu behandelnden Ereignisses in der Basisklasse. Beispiel:  
  
     [!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|Stellt eine Schritt-für-Schritt-Beschreibung des Deklarierens und Auslösens von Ereignissen für eine Klasse bereit.|  
|[Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|Veranschaulicht das Schreiben einer Ereignishandlerprozedur.|  
|[Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|Veranschaulicht die Definition eines benutzerdefinierten Ereignisses, das einen asynchronen Aufruf seiner Ereignishandler zulässt.|  
|[Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|Veranschaulicht die Definition eines benutzerdefinierten Ereignisses, das nur bei der Behandlung des Ereignisses Arbeitsspeicher nutzt.|  
|[Problembehandlung für geerbte Ereignishandler in Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|Führt häufige Probleme auf, die bei Ereignishandlern in geerbten Komponenten auftreten können.|  
|[Ereignisse](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f)|Bietet eine Übersicht über das Ereignismodell in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].|  
|[Erstellen von Ereignishandlern in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx)|Beschreibt die Verwendung von Ereignissen, die Windows Forms-Objekten zugeordnet sind.|  
|[Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|Stellt eine Übersicht über Delegaten in Visual Basic bereit.|
