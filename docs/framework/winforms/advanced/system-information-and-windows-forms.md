---
title: "Systeminformationen und Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6657556ffb49c19e6ffc3ef5462de341a93112b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="4134b-102">Systeminformationen und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4134b-102">System Information and Windows Forms</span></span>
<span data-ttu-id="4134b-103">Manchmal ist es erforderlich, um Informationen über den Computer zu erfassen, die Ihre Anwendung ausgeführt wird, um die Entscheidungen in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="4134b-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="4134b-104">Beispielsweise müssen Sie eine Funktion möglicherweise, die nur anwendbar, wenn mit einer bestimmten Netzwerkdomäne verbunden sind; In diesem Fall müssten Sie eine Möglichkeit, bestimmen Sie die Domäne und die Funktion zu deaktivieren, wenn die Domäne nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4134b-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="4134b-105">Windows Forms-Anwendungen können die <xref:System.Windows.Forms.SystemInformation> Klasse, um eine Reihe von Punkten zu einem Computer, die zur Laufzeit zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4134b-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="4134b-106">Das folgende Beispiel veranschaulicht die Verwendung der <xref:System.Windows.Forms.SystemInformation> Klasse zum Abrufen der <xref:System.Windows.Forms.SystemInformation.UserName%2A> und <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="4134b-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
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
  
 <span data-ttu-id="4134b-107">Alle Mitglieder der <xref:System.Windows.Forms.SystemInformation> Klasse sind schreibgeschützt; Sie Einstellungen eines Benutzers können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4134b-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="4134b-108">Es gibt mehr als 100 Member der Klasse, die zum Zurückgeben von Informationen alles, was von der Anzahl der Monitore an den Computer angeschlossen (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) den Abstand der Symbole in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> und <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="4134b-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="4134b-109">Einige der nützlicher Mitglieder der <xref:System.Windows.Forms.SystemInformation> Klasse einbeziehen <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, und <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span><span class="sxs-lookup"><span data-stu-id="4134b-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4134b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4134b-110">See Also</span></span>  
 <xref:System.Windows.Forms.SystemInformation>  
 [<span data-ttu-id="4134b-111">Energieverwaltung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4134b-111">Power Management in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
