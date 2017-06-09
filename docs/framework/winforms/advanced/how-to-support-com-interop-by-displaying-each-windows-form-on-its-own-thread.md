---
title: "Gewusst wie: Unterst&#252;tzen von COM-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread | Microsoft Docs"
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
  - "COM-Interop, Windows Forms"
  - "COM [Windows Forms]"
  - "Windows Forms, nicht verwaltet"
  - "ActiveX-Steuerelemente [Windows Forms], COM-Interop"
  - "Windows Forms, interop"
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Unterst&#252;tzen von COM-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread
Sie können Probleme mit der COM\-Interoperabilität beheben, indem Sie das Formular in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Nachrichtenschleife anzeigen, die Sie mit der <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>\-Methode erstellen können.  
  
 Damit ein Windows Form aus einer COM\-Clientanwendung heraus ordnungsgemäß funktioniert, müssen Sie das Formular in einer Windows Forms\-Nachrichtenschleife ausführen. Hierzu können Sie einen der folgenden Ansätze verwenden:  
  
-   Verwenden Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode, um das Windows Form anzuzeigen. Weitere Informationen finden Sie unter [Gewusst wie: Unterstützen von COM\-Interop durch Anzeigen eines Windows Forms mit der ShowDialog\-Methode](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Zeigen Sie jedes Windows Form in einem separaten Thread an.  
  
 In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] wird dieses Feature umfassend unterstützt.  
  
 Siehe auch [Exemplarische Vorgehensweise: Unterstützen von COM\-Interop durch das Anzeigen jedes Windows Forms in einem eigenen Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie das Formular über einen separaten Thread anzeigen und die <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>\-Methode aufrufen, um ein Windows Forms\-Nachrichtensystem über diesen Thread zu starten Um diesen Ansatz zu verwenden, müssen Sie jeden Aufruf des Formulars aus der nicht verwalteten Anwendung marshallen, indem Sie die <xref:System.Windows.Forms.Control.Invoke%2A>Methode verwenden.  
  
 Dieser Ansatz erfordert, dass jede Instanz eines Formulars über ihren eigenen Thread ausgeführt wird, indem sie ihre eigene Nachrichtenschleife verwendet. Es ist nicht möglich, mehrere Nachrichtenschleifen pro Thread auszuführen. Daher können Sie die Nachrichtenschleife der Clientanwendung nicht ändern. Sie können jedoch die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Komponente ändern, um einen neuen Thread zu beginnen, der seine eigene Nachrichtenschleife verwendet.  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## Kompilieren des Codes  
  
-   Kompilieren Sie die Typen `COMForm`, `Form1` und `FormManager` in eine Assembly namens `COMWinform.dll`. Registrieren Sie die Assembly für COM\-Interop, indem Sie eine der Methoden verwenden, die unter [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md) beschrieben sind. Sie können die Assembly und deren entsprechende Typbibliotheksdatei \(.tlb\) in nicht verwalteten Anwendungen verwenden. Beispielsweise können Sie die Typbibliothek als Verweis in einem ausführbaren Visual Basic 6.0\-Projekt verwenden.  
  
## Siehe auch  
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)   
 [Registering Assemblies with COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Gewusst wie: Unterstützen von COM\-Interop durch Anzeigen eines Windows Forms mit der ShowDialog\-Methode](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)   
 [Übersicht über Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)