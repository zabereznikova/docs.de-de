---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: bb312317b2bbcb77bed9e3966db6d9fd5db79e4c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396739"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic
Beim Erstellen neuer Anwendungen oder Komponenten empfiehlt es sich, .NET Framework Assemblys zu erstellen. Visual Basic ist es jedoch auch einfach, eine .NET Framework Komponente für com verfügbar zu machen. Dies ermöglicht es Ihnen, neue Komponenten für frühere Anwendungs Suites bereitzustellen, die COM-Komponenten erfordern. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit Visual Basic .NET Framework-Objekte als COM-Objekte verfügbar machen, sowohl mit als auch ohne die com-Klassen Vorlage.  
  
 Die einfachste Möglichkeit, com-Objekte verfügbar zu machen, ist die Verwendung der com-Klassen Vorlage. Die com-Klassen Vorlage erstellt eine neue Klasse und konfiguriert dann das Projekt, um die Klasse und die Interoperabilitäts Schicht als COM-Objekt zu generieren und Sie beim Betriebssystem zu registrieren.  
  
> [!NOTE]
> Obwohl Sie eine Klasse, die in Visual Basic erstellt wurde, auch als COM-Objekt für nicht verwalteten Code verfügbar machen können, handelt es sich nicht um ein echtes com-Objekt, das nicht von Visual Basic verwendet werden kann. Weitere Informationen finden Sie unter [com-Interoperabilität in .NET Framework Anwendungen](com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>So erstellen Sie ein COM-Objekt mithilfe der com-Klassen Vorlage  
  
1. Öffnen Sie über das Menü **Datei** ein neues Windows-Anwendungsprojekt, indem Sie auf **Neues Projekt**klicken.  
  
2. Überprüfen Sie im Dialogfeld **Neues Projekt** unter dem Feld **Projekttypen** , ob Windows ausgewählt ist. Wählen Sie in der Liste **Vorlagen** die Option **Klassenbibliothek** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4. Wählen Sie **com-Klasse** aus der Liste **Vorlagen** aus, und klicken Sie dann auf **Hinzufügen**. Visual Basic fügt eine neue Klasse hinzu und konfiguriert das neue Projekt für COM-Interop.  
  
5. Fügen Sie der com-Klasse Code hinzu, z. b. Eigenschaften, Methoden und Ereignisse.  
  
6. Wählen Sie im Menü **Erstellen** die Option **Build ClassLibrary1** aus. Visual Basic erstellt die Assembly und registriert das COM-Objekt beim Betriebssystem.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Erstellen von COM-Objekten ohne die com-Klassen Vorlage  
 Sie können eine COM-Klasse auch manuell erstellen, anstatt die com-Klassen Vorlage zu verwenden. Diese Vorgehensweise ist hilfreich, wenn Sie über die Befehlszeile arbeiten oder wenn Sie mehr Kontrolle darüber haben möchten, wie COM-Objekte definiert werden.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>So richten Sie das Projekt ein, um ein COM-Objekt zu generieren  
  
1. Öffnen Sie über das Menü **Datei** ein neues Windows-Anwendungsprojekt, indem Sie auf **NewProject**klicken.  
  
2. Überprüfen Sie im Dialogfeld **Neues Projekt** unter dem Feld **Projekttypen** , ob Windows ausgewählt ist. Wählen Sie in der Liste **Vorlagen** die Option **Klassenbibliothek** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**. Der **Projekt-Designer** wird angezeigt.  
  
4. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
5. Aktivieren Sie das Kontrollkästchen **für COM-Interop registrieren** .  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>So richten Sie den Code in der Klasse ein, um ein COM-Objekt zu erstellen  
  
1. Doppelklicken Sie in **Projektmappen-Explorer**auf **Class1. vb** , um den Code anzuzeigen.  
  
2. Ändern Sie den Namen der Klasse in `ComClass1`.  
  
3. Fügen Sie die folgenden Konstanten hinzu `ComClass1` . Sie speichern die GUID-Konstanten (Global Unique Identifier), die für die COM-Objekte erforderlich sind.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**. Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**. Klicken Sie auf **Beenden**.  
  
5. Ersetzen Sie die leere Zeichenfolge `ClassId` durch die GUID, und entfernen Sie die führenden und nachfolgenden geschweiften Klammern. Wenn die von Guidgen bereitgestellte GUID z. b `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` . lautet, sollte der Code wie folgt aussehen.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. Wiederholen Sie die vorherigen Schritte für die `InterfaceId` `EventsId` Konstanten und, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. Andernfalls könnte die COM-Komponente mit anderen COM-Komponenten in Konflikt stehen.  
  
7. Fügen Sie das- `ComClass` Attribut hinzu `ComClass1` , und geben Sie die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID an, wie im folgenden Beispiel gezeigt  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. COM-Klassen müssen über einen Parameter losen `Public Sub New()` Konstruktor verfügen, oder die Klasse wird nicht ordnungsgemäß registriert. Fügen Sie der-Klasse einen Parameter losen Konstruktor hinzu:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Fügen Sie der-Klasse Eigenschaften, Methoden und Ereignisse hinzu, und beenden Sie Sie mit einer- `End Class` Anweisung. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus. Visual Basic erstellt die Assembly und registriert das COM-Objekt beim Betriebssystem.  
  
    > [!NOTE]
    > Die mit Visual Basic generierten COM-Objekte können von anderen Visual Basic Anwendungen nicht verwendet werden, da es sich nicht um echte COM-Objekte handelt. Versuche, Verweise auf solche COM-Objekte hinzuzufügen, geben einen Fehler aus. Weitere Informationen finden Sie unter [com-Interoperabilität in .NET Framework Anwendungen](com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [COM-Interop](index.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](walkthrough-implementing-inheritance-with-com-objects.md)
- [#Region-Direktive](../../language-reference/directives/region-directive.md)
- [COM-Interoperabilität in .NET Framework-Anwendungen](com-interoperability-in-net-framework-applications.md)
- [Problembehandlung bei der Interoperabilität](troubleshooting-interoperability.md)
