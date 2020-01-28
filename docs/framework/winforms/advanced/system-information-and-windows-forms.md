---
title: Systeminformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732588"
---
# <a name="system-information-and-windows-forms"></a>Systeminformationen und Windows Forms
Manchmal ist es erforderlich, Informationen zu dem Computer zu sammeln, auf dem Ihre Anwendung ausgeführt wird, um Entscheidungen in Ihrem Code zu treffen. Beispielsweise können Sie über eine Funktion verfügen, die nur anwendbar ist, wenn eine Verbindung mit einer bestimmten Netzwerk Domäne besteht. in diesem Fall benötigen Sie eine Möglichkeit, die Domäne zu bestimmen und die Funktion zu deaktivieren, wenn die Domäne nicht vorhanden ist.  
  
 Windows Forms Anwendungen können die <xref:System.Windows.Forms.SystemInformation>-Klasse verwenden, um zur Laufzeit eine Reihe von Dingen zu einem Computer zu ermitteln. Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Forms.SystemInformation>-Klasse zum Abrufen der <xref:System.Windows.Forms.SystemInformation.UserName%2A> und <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>veranschaulicht:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 Alle Member der <xref:System.Windows.Forms.SystemInformation>-Klasse sind schreibgeschützt. die Einstellungen eines Benutzers können nicht geändert werden. Es gibt mehr als 100 Mitglieder der-Klasse, die Informationen über die Anzahl der Monitore, die mit dem Computer verbunden sind (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) bis zum Abstand von Symbolen in Windows-Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> und <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>) zurückgeben.  
  
 Zu den nützlicheren Membern der <xref:System.Windows.Forms.SystemInformation>-Klasse gehören <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>und <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SystemInformation>
- [Energieverwaltung in Windows Forms](power-management-in-windows-forms.md)
