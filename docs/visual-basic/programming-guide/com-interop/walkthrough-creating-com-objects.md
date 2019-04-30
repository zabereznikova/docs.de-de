---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekte in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 97e917d568b31860979e54598350d1ae7a6fdb25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022310"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen von COM-Objekte in Visual Basic
Wenn Sie neue Anwendungen oder Komponenten erstellen möchten, empfiehlt es sich zum Erstellen von .NET Framework-Assemblys. Allerdings erleichtert Visual Basic auch .NET Framework-Komponenten für COM verfügbar gemacht. Dadurch können Sie frühere anwendungssuites neue Komponenten bereit, die COM-Komponenten erfordern. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Visual Basic verwenden, um verfügbar zu machen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Objekte als COM-Objekte mit und ohne COM-Klassenvorlage.  
  
 Die einfachste Möglichkeit zum COM-Objekte verfügbar zu machen, ist die Verwendung von COM-Klassenvorlage. COM-Klassenvorlage erstellt eine neue Klasse, und klicken Sie dann Ihr Projekt zum Generieren der Klasse und Interoperabilität-Schicht als COM-Objekt, und registrieren Sie ihn mit dem Betriebssystem konfiguriert.  
  
> [!NOTE]
>  Obwohl Sie auch eine Klasse, die in Visual Basic erstellt werden, als für nicht verwalteten Code mit COM-Objekt verfügbar machen können, ist nicht "true" COM-Objekt und kann nicht von Visual Basic verwendet werden. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>So erstellen Sie ein COM-Objekt mit der COM-Klassenvorlage  
  
1. Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** Menü, indem Sie auf **neues Projekt**.  
  
2. In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows ausgewählt ist. Wählen Sie **Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3. Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4. Wählen Sie **COM-Klasse** aus der **Vorlagen** aus, und klicken Sie dann auf **hinzufügen**. Visual Basic fügt eine neue Klasse hinzu, und konfiguriert das neue Projekt für COM-Interop.  
  
5. Fügen Sie Code wie z. B. Eigenschaften, Methoden und Ereignisse, auf die COM-Klasse.  
  
6. Wählen Sie **erstellen ClassLibrary1** aus der **erstellen** Menü. Visual Basic wird die Assembly erstellt und registriert das COM-Objekt mit dem Betriebssystem.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Erstellen von COM-Objekten ohne COM-Klassenvorlage  
 Sie können auch eine COM-Klasse anstelle von COM-Klassenvorlage manuell erstellen. Dieses Verfahren ist hilfreich, wenn Sie über die Befehlszeile arbeiten oder besser steuern, wie COM-Objekte definiert werden sollen.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Ihr Projekt einrichten, um ein COM-Objekt zu generieren.  
  
1. Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** Menü, indem Sie auf **NewProject**.  
  
2. In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows ausgewählt ist. Wählen Sie **Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**. Die **Projekt-Designer** wird angezeigt.  
  
4. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
5. Wählen Sie die **für COM-Interop registrieren** Kontrollkästchen.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Der Code in Ihrer Klasse einrichten, um ein COM-Objekt zu erstellen.  
  
1. In **Projektmappen-Explorer**, doppelklicken Sie auf **"Class1.vb"** der Code angezeigt werden soll.  
  
2. Benennen Sie die Klasse in `ComClass1` um.  
  
3. Fügen Sie die folgenden Konstanten zum `ComClass1`. Sie speichert die global eindeutige Bezeichner (GUID)-Konstanten, die die COM-Objekte erforderlich sind.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**. Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**. Klicken Sie auf **Schließen**.  
  
5. Ersetzen Sie die leere Zeichenfolge für die `ClassId` durch die GUID, entfernen Sie die führende und nachgestellte geschweifte Klammern. Ist z. B. wenn die GUID von Guidgen angegeben `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` und klicken Sie dann der Code wie folgt angezeigt werden soll.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. Wiederholen Sie die vorherigen Schritte für die `InterfaceId` und `EventsId` Konstanten, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. Andernfalls kann die COM-Komponente mit anderen COM_Komponenten in Konflikt stehen.  
  
7. Hinzufügen der `ComClass` Attribut `ComClass1`, geben Sie die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. COM-Klassen müssen eine parameterlose `Public Sub New()` Konstruktor oder die Klasse wird nicht ordnungsgemäß registriert. Fügen Sie einen parameterlosen Konstruktor der Klasse hinzu:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Hinzufügen von Eigenschaften, Methoden und Ereignisse der Klasse, und endet mit einem `End Class` Anweisung. Wählen Sie **Projektmappe** aus der **erstellen** Menü. Visual Basic wird die Assembly erstellt und registriert das COM-Objekt mit dem Betriebssystem.  
  
    > [!NOTE]
    >  Die COM-Objekte, die Sie mit Visual Basic generieren können nicht von anderen Visual Basic-Anwendungen verwendet werden, da sie nicht "true" COM-Objekte sind. Versucht, Verweise auf diese COM-Objekte hinzufügen, werden ein Fehler ausgelöst. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
- [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
