---
title: "Walkthrough: Creating COM Objects with Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM interop, creating COM objects"
  - "COM objects, creating"
  - "COM interop, walkthroughs"
  - "object creation, COM objects"
  - "COM objects, walkthroughs"
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Walkthrough: Creating COM Objects with Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie neue Anwendungen oder Komponenten erstellen, ist es am sinnvollsten, .NET Framework\-Assemblys zu erstellen.  Mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] können .NET Framework\-Komponenten jedoch auch problemlos für COM zur Verfügung gestellt werden.  So können neue Komponenten für ältere Anwendungen bereitgestellt werden, die COM\-Komponenten erfordern.  In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verwenden, um [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Objekte sowohl mit als auch ohne COM\-Klassenvorlage als COM\-Objekte verfügbar zu machen.  
  
 Am einfachsten können Sie COM\-Objekte mit der COM\-Klassenvorlage zur Verfügung stellen.  Die COM\-Klassenvorlage erstellt eine neue Klasse und konfiguriert anschließend das Projekt, um die Klasse und die Interoperabilitätsschicht als COM\-Objekt zu generieren und dieses anschließend im Betriebssystem zu registrieren.  
  
> [!NOTE]
>  Sie können zwar auch eine mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellte Klasse als COM\-Objekt für nicht verwalteten Code verfügbar machen, allerdings handelt es sich dann nicht um ein echtes COM\-Objekt. Dieses Objekt kann in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] nicht verwendet werden.  Weitere Informationen finden Sie unter [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So erstellen Sie ein COM\-Objekt mit der COM\-Klassenvorlage  
  
1.  Klicken Sie im Menü **Datei** auf **Neues Projekt**, um ein neues Windows\-Anwendungsprojekt zu öffnen.  
  
2.  Überprüfen Sie im Dialogfeld **Neues Projekt** unter dem Feld **Projekttypen**, ob Windows ausgewählt ist.  Markieren Sie in der Liste **Vorlagen** den Eintrag **Klassenbibliothek**, und klicken Sie dann auf **OK**.  Das neue Projekt wird angezeigt.  
  
3.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
4.  Wählen Sie **COM\-Klasse** aus der Liste **Vorlagen**, und klicken Sie dann auf **Hinzufügen**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] fügt eine neue Klasse hinzu und konfiguriert das neue Projekt für COM\-Interop.  
  
5.  Fügen Sie zur COM\-Klasse Code hinzu, z. B. Eigenschaften, Methoden und Ereignisse.  
  
6.  Wählen Sie im Menü **Erstellen** die Option **ClassLibrary1 erstellen**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellt die Assembly und registriert das COM\-Objekt im Betriebssystem.  
  
## Erstellen von COM\-Objekten ohne die COM\-Klassenvorlage  
 Sie können eine COM\-Klasse auch manuell ohne Verwendung der COM\-Klassenvorlage erstellen.  Dieses Vorgehen wird empfohlen, wenn Sie mit der Befehlszeile arbeiten, oder wenn Sie mehr Kontrolle über die Definition von COM\-Objekten wünschen.  
  
#### So richten Sie das Projekt für das Generieren eines COM\-Objekts ein  
  
1.  Klicken Sie im Menü **Datei** auf **Neues Projekt**, um ein neues Windows\-Anwendungsprojekt zu öffnen.  
  
2.  Überprüfen Sie im Dialogfeld **Neues Projekt** unter dem Feld **Projekttypen**, ob Windows ausgewählt ist.  Markieren Sie in der Liste **Vorlagen** den Eintrag **Klassenbibliothek**, und klicken Sie dann auf **OK**.  Das neue Projekt wird angezeigt.  
  
3.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  Der **Projekt\-Designer** wird geöffnet.  
  
4.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
5.  Aktivieren Sie das Kontrollkästchen **Für COM\-Interop registrieren**.  
  
#### So richten Sie den Code der Klasse für das Erstellen eines COM\-Objekts ein  
  
1.  Doppelklicken Sie im **Projektmappen\-Explorer** auf **Class1.vb**, um den Code dieser Klasse anzuzeigen.  
  
2.  Benennen Sie die Klasse in `ComClass1` um.  
  
3.  Fügen Sie zu `ComClass1` die folgenden Konstanten hinzu.  Damit werden die Konstanten der global eindeutigen Bezeichner \(GUID – Globally Unique Identifier\) gespeichert, über die die COM\-Objekte verfügen müssen.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#2)]  
  
4.  Klicken Sie im Menü **Extras** auf **GUID erstellen**.  Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.  Klicken Sie auf **Beenden**.  
  
5.  Ersetzen Sie die leere Zeichenfolge für die `ClassId` durch die GUID, und entfernen Sie die führende sowie die nachfolgende geschweifte Klammer.  Wenn die von Guidgen bereitgestellte GUID z. B. `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` lautet, muss der Code folgendermaßen lauten.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#3)]  
  
6.  Wiederholen Sie wie im folgenden Beispiel die vorherigen Schritte für die `InterfaceId`\-Konstante und die `EventsId`\-Konstante.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#4)]  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass die GUIDs neu und eindeutig sind; andernfalls erzeugt Ihre COM\-Komponente Konflikte mit anderen COM\-Komponenten.  
  
7.  Fügen Sie `ComClass1` das `ComClass`\-Attribut hinzu, und geben Sie die GUIDs für die Klassen\-ID, die Schnittstellen\-ID und die Ereignis\-ID wie im folgenden Beispiel an:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#5)]  
  
8.  COM\-Klassen müssen über einen parameterlosen `Public Sub New()`\-Konstruktor verfügen. Andernfalls kann die Klasse nicht ordnungsgemäß registriert werden.  Fügen Sie der Klasse einen parameterlosen Konstruktor hinzu:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#6)]  
  
9. Fügen Sie der Klasse Eigenschaften, Methoden und Ereignisse hinzu, und beenden Sie die Eingabe mit einer `End Class`\-Anweisung.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellt die Assembly und registriert das COM\-Objekt im Betriebssystem.  
  
    > [!NOTE]
    >  Die mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] generierten COM\-Objekte können nicht von anderen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Anwendungen verwendet werden, da es sich nicht um echte COM\-Objekte handelt.  Wenn Sie versuchen, Verweise auf solche COM\-Objekte hinzuzufügen, tritt ein Fehler auf.  Ausführliche Informationen finden Sie unter [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)   
 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)