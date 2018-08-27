---
title: Gespeicherte CLR-Prozeduren
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: df323e2d1b50dcd1b2087141deefa1c86723b346
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930111"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="dc4fb-102">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="dc4fb-102">CLR Stored Procedures</span></span>
<span data-ttu-id="dc4fb-103">Gespeicherte Prozeduren sind Routinen, die nicht in skalaren Ausdrücken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dc4fb-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="dc4fb-104">Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="dc4fb-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc4fb-105">Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="dc4fb-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="dc4fb-106">Sie müssen angeben, dass der Parameter als Verweis übergeben, und wenden Sie die \<Out() >-Attribut einen Output-Parameter, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="dc4fb-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="dc4fb-107">Weitere Informationen finden Sie unter der Version von [SQL Server-Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc4fb-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="dc4fb-108">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="dc4fb-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="dc4fb-109">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="dc4fb-109">CLR Stored Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="dc4fb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc4fb-110">See Also</span></span>  
 [<span data-ttu-id="dc4fb-111">Erstellen von SQL Server 2005-Objekte In verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="dc4fb-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="dc4fb-112">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="dc4fb-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
