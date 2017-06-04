---
title: "Systeminformationen und Windows&#160;Forms | Microsoft Docs"
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
  - "Domänennamen, Abrufen"
  - "Systeminformationen [Windows Forms]"
  - "SystemInformation-Klasse [Windows Forms]"
  - "Benutzernamen, Abrufen"
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Systeminformationen und Windows&#160;Forms
Für eine sinnvolle Programmierung ist es u. U. erforderlich, Informationen über den Computer zu erfassen, auf dem die jeweilige Anwendung ausgeführt wird.  Beispielsweise könnte eine Funktion nur dann anwendbar sein, wenn eine Verbindung zu einer bestimmten Netzwerkdomäne besteht. In diesem Fall müsste es eine Möglichkeit geben, die Domäne zu ermitteln und die Funktion zu deaktivieren, falls die erforderliche Domäne nicht vorhanden ist.  
  
 Mithilfe der <xref:System.Windows.Forms.SystemInformation>\-Klasse können Windows Forms\-Anwendungen zur Laufzeit eine Reihe von Informationen über einen Computer abfragen.  Im folgenden Beispiel wird erläutert, wie Sie mithilfe der <xref:System.Windows.Forms.SystemInformation>\-Klasse den <xref:System.Windows.Forms.SystemInformation.UserName%2A> und den <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A> abrufen:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 Alle Member der <xref:System.Windows.Forms.SystemInformation>\-Klasse sind schreibgeschützt, sodass die Einstellungen eines Benutzers nicht geändert werden können.  Die Klasse verfügt über mehr als 100 Member, die unterschiedlichste Informationen – von der Anzahl der an den Computer angeschlossenen Monitore \(<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>\) bis hin zum Abstand der Symbole in Windows Explorer \(<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> und <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>\) – zurückgeben.  
  
 Zu den wichtigsten Membern der <xref:System.Windows.Forms.SystemInformation>\-Klasse gehören <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> und <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.SystemInformation>   
 [Energieverwaltung in Windows Forms](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)