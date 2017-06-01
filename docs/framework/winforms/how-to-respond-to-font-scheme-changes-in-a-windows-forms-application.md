---
title: "Gewusst wie: Reagieren auf &#196;nderungen des Schriftartenschemas in einer Windows Forms-Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, Schriftartenschemas"
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Reagieren auf &#196;nderungen des Schriftartenschemas in einer Windows Forms-Anwendung
In den Windows\-Betriebssystemen kann ein Benutzer die systemweiten Schriftarteinstellungen ändern, damit die Standardschriftart größer oder kleiner angezeigt wird.  Das Ändern dieser Schriftarteinstellungen ist besonders für sehbehinderte Benutzer von Bedeutung, die auf größere Schriftarten angewiesen sind, um den Text auf dem Bildschirm lesen zu können.  Sie können die Windows Forms\-Anwendung anpassen, sodass die Größe des Formulars und des darin enthaltenen Textes zu\- oder abnimmt, wenn sich das Schriftartschema ändert.  Wenn sich das Formular bei Änderungen der Schriftartgröße dynamisch anpassen soll, können Sie dem Formular Code hinzufügen.  
  
 Die Standardschriftart von Windows Forms ist in der Regel die Schriftart, die vom <xref:Microsoft.Win32>\-Namespace beim Aufrufen von `GetStockObject(DEFAULT_GUI_FONT)` zurückgegeben wird.  Die von diesem Aufruf zurückgegebene Schriftart ändert sich nur, wenn sich die Bildschirmauflösung ändert.  Wie in der folgenden Prozedur gezeigt, muss der Code die Standardschriftart in <xref:System.Drawing.SystemFonts.IconTitleFont%2A> ändern, damit bei Änderungen der Schriftartgröße entsprechend reagiert wird.  
  
### So verwenden Sie die Desktopschriftart und reagieren auf Änderungen des Schriftartschemas  
  
1.  Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Windows Forms\-Anwendungen über die Befehlszeile](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) und [Steuerelemente für Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Fügen Sie im Code einen Verweis auf den <xref:Microsoft.Win32>\-Namespace hinzu.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Fügen Sie dem Konstruktor folgenden Code des Formulars hinzu, um die erforderlichen Ereignishandler zu verknüpfen und die für das Formular verwendete Standardschriftart zu ändern.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Implementieren Sie einen Handler für das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>\-Ereignis, durch den das Formular automatisch skaliert wird, wenn sich die <xref:Microsoft.Win32.UserPreferenceCategory>\-Kategorie ändert.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Implementieren Sie zuletzt einen Handler für das <xref:System.Windows.Forms.Form.FormClosing>\-Ereignis, durch den der <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>\-Ereignishandler getrennt wird.  
  
> [!IMPORTANT]
>  Wenn Sie diesen Code nicht verwenden, führt dies zu Speicherverlust in der Anwendung.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  Kompilieren Sie den Code, und führen Sie ihn aus.  
  
### So ändern Sie das Schriftartschema in Windows XP manuell  
  
1.  Starten Sie die Windows Forms\-Anwendung, klicken Sie mit der rechten Maustaste auf den Windows\-Desktop, und wählen Sie im Kontextmenü **Eigenschaften** aus.  
  
2.  Klicken Sie im Dialogfeld **Eigenschaften von Anzeige** auf die Registerkarte **Darstellung**.  
  
3.  Wählen Sie in der Dropdownliste **Grad** einen neuen Schriftgrad aus.  
  
     Beachten Sie, dass das Formular nun auf Laufzeitänderungen im Desktopschriftartschema reagiert.  Wenn der Benutzer zwischen **Standard**, **Groß** und **Extragroß** wechselt, ändern sich die Schriftart und die Skalierung des Formulars entsprechend.  
  
## Beispiel  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Der Konstruktor in diesem Codebeispiel enthält einen Aufruf an `InitializeComponent`, der definiert wird, wenn Sie ein neues Windows Forms\-Projekt in Visual Studio erstellen.  Entfernen Sie diese Codezeile, wenn Sie die Anwendung in der Befehlszeile erstellen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>   
 [Automatische Skalierung in Windows Forms](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)