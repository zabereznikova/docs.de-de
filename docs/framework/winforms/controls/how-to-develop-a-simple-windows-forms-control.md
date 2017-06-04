---
title: "Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Control-Klasse, Windows Forms"
  - "Steuerelemente [Windows Forms]"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Erstellen einfacher Steuerelemente mithilfe von Code"
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements
In diesem Abschnitt werden die wesentlichen Schritte beim Erstellen benutzerdefinierter Windows Forms\-Steuerelemente behandelt.  In dieser exemplarischen Vorgehensweise wird ein einfaches Steuerelement entwickelt, das die Änderung der Ausrichtung seiner <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft zulässt.  Es dient nicht zum Behandeln oder Auslösen von Ereignissen.  
  
### So erstellen Sie ein einfaches benutzerdefiniertes Steuerelement  
  
1.  Definieren Sie eine Klasse, die von <xref:System.Windows.Forms.Control?displayProperty=fullName> abgeleitet wird.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  Definieren Sie Eigenschaften.  \(Die Definition von Eigenschaften ist nicht zwingend erforderlich, da ein Steuerelement viele Eigenschaften von der <xref:System.Windows.Forms.Control>\-Klasse erbt. Jedoch definieren im Allgemeinen die meisten benutzerdefinierten Steuerelemente zusätzliche Eigenschaften.\) Im folgenden Codefragment wird eine Eigenschaft mit dem Namen `TextAlignment` definiert. Sie wird von `FirstControl`  dazu verwendet, die Anzeige der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft zu formatieren, die von <xref:System.Windows.Forms.Control> geerbt wurde.  Weitere Informationen über das Definieren von Eigenschaften finden Sie unter [Properties Overview](../Topic/Properties%20Overview.md).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     Wenn Sie eine Eigenschaft festlegen, durch die die visuelle Darstellung eines Steuerelements geändert wird, müssen Sie die <xref:System.Windows.Forms.Control.Invalidate%2A>\-Methode aufrufen, um das Steuerelement neu zu zeichnen.  <xref:System.Windows.Forms.Control.Invalidate%2A> ist in der Basisklasse <xref:System.Windows.Forms.Control> definiert.  
  
3.  Überschreiben Sie die geschützte, von <xref:System.Windows.Forms.Control> geerbte <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode, um dem Steuerelement Renderinglogik zur Verfügung zu stellen.  Wenn Sie <xref:System.Windows.Forms.Control.OnPaint%2A> nicht überschreiben, wird das Steuerelement nicht in die Lage versetzt, sich selbst zu zeichnen.  Im folgenden Codefragment zeigt die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode die von <xref:System.Windows.Forms.Control> geerbte <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft mit der durch das `alignmentValue`\-Feld festgelegten Ausrichtung an.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  Stellen Sie Attribute für das Steuerelement bereit.  Durch Attribute kann das Steuerelement samt seiner Eigenschaften und Ereignisse zur Entwurfszeit in einem visuellen Designer entsprechend angezeigt werden.  Im folgenden Codefragment werden Attribute auf die `TextAlignment`\-Eigenschaft angewendet.  Das <xref:System.ComponentModel.CategoryAttribute.Category%2A>\-Attribut \(das im Codefragment gezeigt wird\) führt in einem Designer wie Visual Studio dazu, dass die Eigenschaft in einer logischen Kategorie angezeigt wird.  Das <xref:System.ComponentModel.DescriptionAttribute.Description%2A>\-Attribut bewirkt bei Auswahl der `TextAlignment`\-Eigenschaft, dass eine beschreibende Zeichenfolge am unteren Rand des **Eigenschaftenfensters** angezeigt wird.  Weitere Informationen über Attribute finden Sie unter [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  \(Optional\) Stellen Sie Ressourcen für das Steuerelement bereit.  Sie können dem Steuerelement eine Ressource \(z. B. eine Bitmap\) zur Verfügung stellen, indem Sie eine Compileroption \(`/res` für C\#\) zum Verpacken von Ressourcen mit dem Steuerelement verwenden.  Zur Laufzeit kann die Ressource mit den Methoden der <xref:System.Resources.ResourceManager>\-Klasse abgerufen werden.  Weitere Informationen über das Erstellen und Verwenden von Ressourcen finden Sie unter [Ressourcen in Desktop\-Apps](../../../../docs/framework/resources/index.md).  
  
6.  Kompilieren Sie das Steuerelement, und geben Sie es weiter.  Zum Kompilieren und zur Bereitstellung von `FirstControl,` führen Sie folgende Schritte aus:  
  
    1.  Speichern Sie den Code im folgenden Beispiel als Quelldatei \(z. B. als **FirstControl.cs** oder **FirstControl.vb**\).  
  
    2.  Kompilieren Sie den Quellcode in eine Assembly, und speichern Sie diese im Anwendungsverzeichnis.  Führen Sie dazu den folgenden Befehl im Verzeichnis aus, das die Quelldatei enthält.  
  
        ```vb  
        vbc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```csharp  
        csc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.cs  
        ```  
  
         Durch die Compileroption `/t:library` wird dem Compiler mitgeteilt, dass es sich bei der von Ihnen erstellten Assembly um eine Bibliothek und nicht um eine ausführbare Datei handelt.  Durch die Option `/out` werden Pfad und Name der Assembly festgelegt.  Die Option `/r` stellt den Namen der Assemblys bereit, auf die der Code verweist.  In diesem Beispiel erstellen Sie eine private Assembly, die ausschließlich Ihre Anwendung verwenden kann.  Daher müssen Sie sie in Ihrem Anwendungsverzeichnis speichern.  Weitere Informationen über das Packen und Bereitstellen eines Steuerelements zur Verteilung finden Sie unter [Bereitstellung](../../../../docs/framework/deployment/net-framework-and-applications.md).  
  
 Im Folgenden wird der Code für `FirstControl` gezeigt.  Das Steuerelement ist im Namespace `CustomWinControls` eingeschlossen.  Ein Namespace stellt eine logische Gruppe verwandter Typen bereit.  Sie können ein Steuerelement in einem neuen oder vorhandenen Namespace erstellen.  `using`\-Deklarationen \(`Imports` in Visual Basic\) ermöglichen in C\# den Zugriff auf Typen über einen Namespace ohne Verwendung des vollständigen Typnamens.  Im folgenden Beispiel ermöglicht es die `using`\-Deklaration, dass Code die <xref:System.Windows.Forms.Control>\-Klasse aus <xref:System.Windows.Forms?displayProperty=fullName> einfach als <xref:System.Windows.Forms.Control> aufrufen kann, anstatt den vollständig qualifizierten Namen <xref:System.Windows.Forms.Control?displayProperty=fullName> verwenden zu müssen.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## Verwenden des benutzerdefinierten Steuerelements in einem Formular  
 Im folgenden Beispiel wird ein einfaches Formular gezeigt, das `FirstControl` verwendet.  Es werden drei Instanzen von `FirstControl` mit unterschiedlichen Werten für die `TextAlignment`\-Eigenschaft erstellt.  
  
#### So kompilieren Sie dieses Beispiel und führen es aus  
  
1.  Speichern Sie den Code im folgenden Beispiel als Quelldatei \(**SimpleForm.cs** oder **SimpleForms.vb**\).  
  
2.  Kompilieren Sie den Quellcode in eine ausführbare Assembly. Führen Sie dazu den folgenden Befehl in dem Verzeichnis aus, das die Quelldatei enthält.  
  
    ```vb  
    vbc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```csharp  
    csc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     CustomWinControls.dll ist die Assembly, die die Klasse`FirstControl`enthält.  Diese Assembly muss sich im selben Verzeichnis befinden wie die Quelldatei des Formulars, das auf sie zugreift \(**SimpleForm.cs** oder **SimpleForms.vb**\).  
  
3.  Führen Sie **SimpleForm.exe** mit folgendem Befehl aus.  
  
    ```  
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## Siehe auch  
 [Eigenschaften von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Ereignisse in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)