---
title: Gespeicherte CLR-Prozeduren
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 9b31d93c1ebc0af9aa8e41b3a4c328af62da7e23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230810"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="b3275-102">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b3275-102">CLR Stored Procedures</span></span>
<span data-ttu-id="b3275-103">Gespeicherte Prozeduren sind Routinen, die nicht in skalaren Ausdrücken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b3275-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="b3275-104">Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b3275-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3275-105">Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b3275-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="b3275-106">Sie müssen angeben, dass der Parameter als Verweis übergeben, und wenden Sie die \<Out() >-Attribut einen Output-Parameter, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b3275-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="b3275-107">Weitere Informationen finden Sie unter der Version von [SQL Server-Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3275-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 **<span data-ttu-id="b3275-108">SQL Server-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="b3275-108">SQL Server documentation</span></span>**

1. [<span data-ttu-id="b3275-109">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b3275-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="b3275-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3275-110">See also</span></span>

- [<span data-ttu-id="b3275-111">Erstellen von SQL Server 2005-Objekte In verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="b3275-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [<span data-ttu-id="b3275-112">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b3275-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
