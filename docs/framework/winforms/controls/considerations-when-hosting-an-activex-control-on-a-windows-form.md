---
title: "&#220;berlegungen zum Integrieren eines ActiveX-Steuerelements in ein Windows&#160;Form | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [Windows Forms], Hinzufügen"
  - "ActiveX-Steuerelemente [Windows Forms], Hosting"
  - "Windows Forms-Steuerelemente, ActiveX-Steuerelemente"
  - "Windows Forms, ActiveX-Steuerelemente"
  - "Windows Forms, Hosting von ActiveX-Steuerelementen"
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;berlegungen zum Integrieren eines ActiveX-Steuerelements in ein Windows&#160;Form
Obwohl Windows Forms für die Aufnahme von Windows Forms\-Steuerelementen optimiert sind, können Sie weiterhin ActiveX\-Steuerelemente verwenden.  Bei Verwendung von ActiveX\-Steuerelementen in einer Anwendung sollten Sie Folgendes berücksichtigen:  
  
-   **Sicherheit** Die Common Language Runtime wurde im Hinblick auf die Codezugriffssicherheit verbessert.  Anwendungen mit Windows Forms können in einer voll vertrauenswürdigen Umgebung uneingeschränkt und in einer halb vertrauenswürdigen Umgebung mit Zugriff auf die meisten verfügbaren Funktionen ausgeführt werden.  Steuerelemente für Windows Forms können problemlos in einem Browser integriert werden.  Diese verbesserten Sicherheitsmerkmale können jedoch nicht genutzt werden, wenn ActiveX\-Steuerelemente für Windows Forms verwendet werden.  Zum Ausführen eines ActiveX\-Steuerelements ist die Berechtigung für nicht verwalteten Code erforderlich. Diese wird mit der <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=fullName>\-Eigenschaft festgelegt.  Weitere Informationen über Sicherheit und die Berechtigung für nicht verwalteten Code finden Sie unter [SecurityPermissionAttribute\-Klasse](frlrfSystemSecurityPermissionsSecurityPermissionAttributeClassTopic).  
  
-   **Gesamtkosten** ActiveX\-Steuerelemente, die einem Windows Form hinzugefügt werden, werden komplett mit diesem Windows Form weitergegeben. Dadurch können die erstellten Dateien unter Umständen sehr groß werden.  Außerdem muss bei Verwendung von ActiveX\-Steuerelementen für Windows Forms die Registrierung geändert werden.  Damit wird stärker in den Computer des Benutzers eingegriffen als mit Steuerelementen für Windows Forms, bei denen dies nicht erforderlich ist.  
  
    > [!NOTE]
    >  Zum Arbeiten mit ActiveX\-Steuerelementen ist ein COM\-Interop\-Wrapper erforderlich.  Weitere Informationen finden Sie unter [COM\-Interoperabilität in Visual Basic und Visual C\#](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md).  
  
    > [!NOTE]
    >  Wenn der Name eines Members des ActiveX\-Steuerelements mit einem in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] definierten Namen übereinstimmt, versieht der ActiveX Control Importer den Membernamen mit dem Präfix **Ctl**, wenn die von <xref:System.Windows.Forms.AxHost> abgeleitete Klasse erstellt wird.  Wenn beispielsweise das ActiveX\-Steuerelement ein Member mit dem Namen **Layout** enthält, wird dieser Name in der von AxHost abgeleiteten Klasse in **CtlLayout** geändert, da in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] das **Layout**\-Ereignis bereits definiert ist.  
  
## Siehe auch  
 [Gewusst wie: Hinzufügen von ActiveX\-Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [Code Access Security](../../../../docs/framework/misc/code-access-security.md)   
 [Controls and Programmable Objects Compared in Various Languages and Libraries](http://msdn.microsoft.com/de-de/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Einfügen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)