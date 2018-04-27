---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e660d672fc32455cee349dc44ad20c3244c087b4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic
Für die Erstellung neuer Anwendungen oder Komponenten, empfiehlt es sich um .NET Framework-Assemblys zu erstellen. Allerdings erleichtert Visual Basic auch .NET Framework-Komponenten für COM verfügbar machen. Dadurch können Sie neue Komponenten für frühere Anwendung Sammlungen bereitstellen, die COM-Komponenten erfordern. Diese exemplarische Vorgehensweise veranschaulicht, wie Sie mithilfe von Visual Basic um verfügbar zu machen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Objekte als COM-Objekte, die mit und ohne die COM-Klassenvorlage.  
  
 Die einfachste Möglichkeit zum Verfügbarmachen von COM-Objekten wird mithilfe der Vorlage der COM-Klasse. Die COM-Klassenvorlage wird eine neue Klasse erstellt und konfiguriert anschließend das Projekt, um die Klasse und Interoperabilität Ebene als COM-Objekt zu generieren, und registrieren Sie ihn mit dem Betriebssystem.  
  
> [!NOTE]
>  Obwohl Sie auch eine Klasse, die in Visual Basic erstellt wird, als für nicht verwalteten Code mit COM-Objekt verfügbar gemacht werden können, ist kein "true" COM-Objekt und kann nicht von Visual Basic verwendet werden. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>So erstellen ein COM-Objekt mithilfe der Vorlage der COM-Klasse  
  
1.  Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **neues Projekt**.  
  
2.  In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist. Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3.  Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4.  Wählen Sie **COM-Klasse** aus der **Vorlagen** aus, und klicken Sie dann auf **hinzufügen**. Visual Basic fügt eine neue Klasse hinzu und konfiguriert das neue Projekt für COM-Interop.  
  
5.  Fügen Sie Code, z. B. Eigenschaften, Methoden und Ereignisse, auf die COM-Klasse.  
  
6.  Wählen Sie **erstellen "ClassLibrary1"** aus der **erstellen** Menü. Visual Basic erstellt die Assembly und das COM-Objekt mit dem Betriebssystem registriert.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Erstellen von COM-Objekte, ohne die Vorlage für die COM-Klasse  
 Sie können auch eine COM-Klasse anstelle der COM-Klassenvorlage manuell erstellen. Dieses Verfahren ist hilfreich, bei der Arbeit von der Befehlszeile aus, oder wenn Sie besser steuern, wie COM-Objekte definiert werden soll.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Einrichten Ihres Projekts festlegen, um ein COM-Objekt zu generieren.  
  
1.  Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **neues Projekt**.  
  
2.  In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist. Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**. Die **Projekt-Designer** wird angezeigt.  
  
4.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
5.  Wählen Sie die **für COM-Interop registrieren** Kontrollkästchen.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Richten Sie den Code in Ihrer Klasse zum Erstellen eines COM-Objekts  
  
1.  In **Projektmappen-Explorer**, doppelklicken Sie auf **Class1.vb** um ihren Code anzuzeigen.  
  
2.  Benennen Sie die Klasse in `ComClass1` um.  
  
3.  Fügen Sie die folgenden Konstanten `ComClass1`. Sie werden die Konstanten der global eindeutige Bezeichner (GUID) gespeichert, die die COM-Objekte aufweisen müssen.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**. Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**. Klicken Sie auf **Schließen**.  
  
5.  Ersetzen Sie die leere Zeichenfolge für die `ClassId` mit der GUID entfernen Sie die führende und nachgestellte geschweifte Klammern. Ist beispielsweise, wenn die GUID von Guidgen bereitgestellte `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` und klicken Sie dann der Code wie folgt angezeigt werden soll.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Wiederholen Sie die vorherigen Schritte für die `InterfaceId` und `EventsId` Konstanten, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. andernfalls, COM-Komponente einen Konflikt mit anderen COM-Komponenten.  
  
7.  Hinzufügen der `ComClass` -Attribut `ComClass1`, die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID angeben, wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  COM-Klassen müssen eine parameterlose `Public Sub New()` Konstruktor oder die Klasse wird nicht ordnungsgemäß registriert. Fügen Sie der Klasse einen parameterlosen Konstruktor hinzu:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Hinzufügen von Eigenschaften, Methoden und Ereignisse auf die Klasse, beenden ihn mit einer `End Class` Anweisung. Wählen Sie **Projektmappe** aus der **erstellen** Menü. Visual Basic erstellt die Assembly und das COM-Objekt mit dem Betriebssystem registriert.  
  
    > [!NOTE]
    >  Die COM-Objekte, die Sie mit Visual Basic generieren können nicht von anderen Visual Basic-Anwendungen verwendet werden, da sie nicht auf "true" COM-Objekte sind. Versuche, Verweise auf diese COM-Objekte hinzuzufügen, werden ein Fehler ausgelöst. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)  
 [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
