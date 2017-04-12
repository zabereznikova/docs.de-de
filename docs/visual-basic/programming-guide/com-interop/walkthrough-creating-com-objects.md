---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten mit Visual Basic | Microsoft-Dokumentation'
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
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cce28e2be5914880107334bf2c4dc4dc645b4793
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic
Beim Erstellen neuer Anwendungen oder Komponenten ist es besser, .NET Framework-Assemblys zu erstellen. Allerdings [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erleichtert auch .NET Framework-Komponenten für COM verfügbar gemacht. Dadurch können Sie neue Komponenten für frühere anwendungssuites bereitstellen, die COM-Komponenten erfordern. Diese exemplarische Vorgehensweise veranschaulicht, wie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verfügbar machen [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Objekte als COM-Objekte, die sowohl mit als auch ohne COM-Klassenvorlage.  
  
 Die einfachste Möglichkeit, die COM-Objekte verfügbar machen, wird mithilfe der COM-Klassenvorlage. COM-Klassenvorlage erstellt eine neue Klasse und konfiguriert anschließend das Projekt, um die Klasse und Interoperabilität Ebene als COM-Objekt zu generieren und mit dem Betriebssystem zu registrieren.  
  
> [!NOTE]
>  Obwohl Sie auch eine Klasse erstellt, die zur Verfügung stellen können [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] als COM-Objekt für nicht verwalteten Code verwenden, ist es sich nicht um ein echtes COM-Objekt und kann nicht verwendet werden, indem [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>So erstellen Sie ein COM-Objekt mit der COM-Klassenvorlage  
  
1.  Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **neues Projekt**.  
  
2.  In der **neues Projekt** im Dialogfeld unter den **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist. Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3.  Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü. Die **neues Element hinzufügen** Dialogfeld wird angezeigt.  
  
4.  Wählen Sie **COM-Klasse** aus der **Vorlagen** aus, und klicken Sie dann auf **hinzufügen**. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Fügt eine neue Klasse hinzu und konfiguriert das neue Projekt für COM-Interop.  
  
5.  Fügen Sie Code wie z. B. Eigenschaften, Methoden und Ereignisse, die COM-Klasse.  
  
6.  Wählen Sie **ClassLibrary1 erstellen** aus der **erstellen** Menü. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]erstellt die Assembly und registriert das COM-Objekt mit dem Betriebssystem.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Erstellen von COM-Objekten ohne die COM-Klassenvorlage  
 Sie können auch eine COM-Klasse statt der COM-Klassenvorlage manuell erstellen. Dieses Verfahren ist hilfreich, wenn Sie über die Befehlszeile arbeiten, oder wenn Sie möchten, dass mehr Kontrolle über die Definition von COM-Objekten.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Um Ihr Projekt einzurichten, um ein COM-Objekt zu generieren.  
  
1.  Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **NewProject**.  
  
2.  In der **neues Projekt** im Dialogfeld unter den **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist. Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.  
  
3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**. Die **Projekt-Designer** wird angezeigt.  
  
4.  Klicken Sie auf die **Kompilieren** Registerkarte.  
  
5.  Wählen Sie die **für COM-Interop registrieren** das Kontrollkästchen.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Der Code in der Klasse einrichten, um ein COM-Objekt zu erstellen.  
  
1.  In **Projektmappen-Explorer**, doppelklicken Sie auf **Class1.vb** um den Code anzuzeigen.  
  
2.  Benennen Sie die Klasse in `ComClass1` um.  
  
3.  Fügen Sie die folgenden Konstanten `ComClass1`. Sie speichert die Konstanten der global eindeutige Bezeichner (GUID), die die COM-Objekte erforderlich sind.  
  
     [!code-vb[VbVbalrInterop&#2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  Auf der **Tools** Menü klicken Sie auf **Guid erstellen**. In der **GUID erstellen** im Dialogfeld klicken Sie auf **Registrierungsformat** , und klicken Sie dann auf **Kopie**. Klicken Sie auf **beenden**.  
  
5.  Ersetzen Sie die leere Zeichenfolge für die `ClassId` durch die GUID, entfernen Sie die führende und nachfolgende geschweifte Klammern. Ist z. B. wenn die GUID von Guidgen bereitgestellte `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` und dann der Code wie folgt angezeigt werden soll.  
  
     [!code-vb[VbVbalrInterop&3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Wiederholen Sie die vorherigen Schritte für die `InterfaceId` und `EventsId` Konstanten, wie im folgenden Beispiel.  
  
     [!code-vb[VbVbalrInterop&4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. Andernfalls kann die COM-Komponente mit anderen COM_Komponenten einen Konflikt.  
  
7.  Hinzufügen der `ComClass` -Attribut `ComClass1`, geben Sie die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID wie im folgenden Beispiel:  
  
     [!code-vb[VbVbalrInterop&5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  COM-Klassen müssen eine parameterlose `Public Sub New()` Konstruktor oder die Klasse wird nicht ordnungsgemäß registriert. Fügen Sie der Klasse einen parameterlosen Konstruktor hinzu:  
  
     [!code-vb[VbVbalrInterop&6;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Hinzufügen von Eigenschaften, Methoden und Ereignisse auf die Klasse, und endet mit einem `End Class` Anweisung. Wählen Sie **Projektmappe** aus der **erstellen** Menü. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]erstellt die Assembly und registriert das COM-Objekt mit dem Betriebssystem.  
  
    > [!NOTE]
    >  Die COM-Objekte, die Sie generieren mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kann nicht verwendet werden, von anderen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Applications, da sie nicht auf "true" COM-Objekte sind. Versucht, Verweise auf solche COM-Objekte hinzuzufügen, tritt ein Fehler auf. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md)   
 [COM-Interoperabilität in .NET Framework-Clientanwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
