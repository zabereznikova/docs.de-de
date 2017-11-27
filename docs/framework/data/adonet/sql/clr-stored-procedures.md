---
title: Gespeicherte CLR-Prozeduren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1e55222c16d223a86e1e11ce2b985ec0f4d8eaa3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="579f8-102">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="579f8-102">CLR Stored Procedures</span></span>
<span data-ttu-id="579f8-103">Gespeicherte Prozeduren sind Routinen, die nicht in skalaren Ausdrücken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="579f8-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="579f8-104">Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="579f8-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="579f8-105">Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="579f8-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="579f8-106">Sie müssen angeben, dass der Parameter als Verweis übergeben, und wenden Sie die \<Out() >-Attribut ein Output-Parameter, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="579f8-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 <span data-ttu-id="579f8-107">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="579f8-107">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="579f8-108">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="579f8-108">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="579f8-109">CLR-gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="579f8-109">CLR Stored Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="579f8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="579f8-110">See Also</span></span>  
 [<span data-ttu-id="579f8-111">Erstellen von SQL Server 2005-Objekte In verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="579f8-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="579f8-112">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="579f8-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
