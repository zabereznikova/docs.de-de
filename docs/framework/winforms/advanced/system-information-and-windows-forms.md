---
title: Systeminformationen und Windows Forms
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
ms.openlocfilehash: eeb469dbf4553634aa50d0a9ea17e9b2464defb4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228899"
---
# <a name="system-information-and-windows-forms"></a>Systeminformationen und Windows Forms
Manchmal ist es erforderlich, um Informationen über den Computer zu erfassen, die Ihre Anwendung ausgeführt wird, um in Ihrem Code Entscheidungen zu treffen. Beispielsweise können Sie eine Funktion haben, die nur gültig, wenn es mit einer bestimmten Netzwerkdomäne verbunden sind; In diesem Fall müssten Sie eine Möglichkeit, bestimmen Sie die Domäne und die Funktion zu deaktivieren, wenn die Domäne nicht vorhanden ist.  
  
 Windows Forms-Anwendungen können die <xref:System.Windows.Forms.SystemInformation> Klasse, um eine Reihe von Faktoren zu einem Computer, die zur Laufzeit zu bestimmen. Das folgende Beispiel veranschaulicht die Verwendung der <xref:System.Windows.Forms.SystemInformation> -Klasse zum Abrufen der <xref:System.Windows.Forms.SystemInformation.UserName%2A> und <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
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
  
 Alle Mitglieder der <xref:System.Windows.Forms.SystemInformation> Klasse sind schreibgeschützt; Sie können die Einstellungen eines Benutzers nicht ändern. Es gibt mehr als 100 Member der Klasse, die zum Zurückgeben von Informationen für alles, von der Anzahl der Monitore an den Computer angeschlossen (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) den Abstand der Symbole in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> und <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Einige nützliche Member von der <xref:System.Windows.Forms.SystemInformation> Klasse enthalten <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, und <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SystemInformation>
- [Energieverwaltung in Windows Forms](power-management-in-windows-forms.md)
