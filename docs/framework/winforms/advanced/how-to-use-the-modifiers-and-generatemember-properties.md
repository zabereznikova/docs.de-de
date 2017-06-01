---
title: "Gewusst wie: Verwenden von Modifizierern und GenerateMember-Eigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Designer_GenerateMember"
  - "Designer_Modifiers"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Basisformulare"
  - "Formularvererbung"
  - "GenerateMember-Eigenschaft"
  - "Vererbung, Formulare"
  - "Geerbte Formulare"
  - "Geerbte Formulare, Windows Forms"
  - "Modifiers-Eigenschaft"
  - "Windows Forms, Vererbung"
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verwenden von Modifizierern und GenerateMember-Eigenschaften
Wenn Sie eine Komponente auf einem Windows Form ablegen, werden von der Entwurfsumgebung die folgenden beiden Eigenschaften bereitgestellt: `GenerateMember` und `Modifiers`.  Die `GenerateMember`\-Eigenschaft legt fest, wann der Windows Forms\-Designer eine Membervariable für eine Komponente generiert.  Die `Modifiers`\-Eigenschaft entspricht dem dieser Membervariablen zugewiesenen Zugriffsmodifizierer.  Wenn der Wert der `GenerateMember`\-Eigenschaft `false` lautet, bleibt der Wert der `Modifiers`\-Eigenschaft ohne Wirkung.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie fest, ob eine Komponente ein Member des Formulars ist  
  
1.  Öffnen Sie das Formular im Windows Forms\-Designer.  
  
2.  Öffnen Sie die **Toolbox**, und platzieren Sie drei <xref:System.Windows.Forms.Button>\-Steuerelemente im Formular.  
  
3.  Legen Sie die `GenerateMember`\-Eigenschaft und die `Modifiers`\-Eigenschaft für jedes <xref:System.Windows.Forms.Button>\-Steuerelement entsprechend der folgenden Tabelle fest.  
  
    |Schaltflächenname|GenerateMember\-Wert|Modifiziererwert|  
    |-----------------------|--------------------------|----------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Keine Änderung|  
  
4.  Erstellen Sie die Projektmappe.  
  
5.  Klicken Sie im **Projektmappen\-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  
  
6.  Öffnen Sie den Knoten **Form1** und dann im **Code\-Editor** die Datei **Form1.Designer.vb** oder **Form1.Designer.cs**.  Diese Datei enthält den vom Windows Forms\-Designer ausgegebenen Code.  
  
7.  Suchen Sie die Deklarationen für die drei Schaltflächen.  Im folgenden Codebeispiel werden die Unterschiede veranschaulicht, die aus der Verwendung der `GenerateMember`\-Eigenschaft und der `Modifiers`\-Eigenschaft resultieren.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  Standardmäßig weist der Windows Forms\-Designer den `private`\-Modifizierer \(`Friend` in Visual Basic\) Containersteuerelementen wie <xref:System.Windows.Forms.Panel> zu.  Wenn eine <xref:System.Windows.Forms.UserControl>\-Basis oder eine<xref:System.Windows.Forms.Form>\-Basis ein Containersteuerelement besitzt, akzeptiert sie in den ihr zugeordneten Steuerelementen und Formularen keine untergeordneten Elemente.  Die Lösung besteht darin, den Modifizierer des Basiscontainersteuerelements in `protected` oder `public` zu ändern.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Button>   
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)   
 [Gewusst wie: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)