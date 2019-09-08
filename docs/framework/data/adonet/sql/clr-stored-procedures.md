---
title: Gespeicherte CLR-Prozeduren
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: d2fde4fdcd5ab63906256d814256578b9baa9ecd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782494"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="f852b-102">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f852b-102">CLR Stored Procedures</span></span>
<span data-ttu-id="f852b-103">Gespeicherte Prozeduren sind Routinen, die nicht in skalaren Ausdrücken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f852b-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="f852b-104">Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f852b-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f852b-105">Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="f852b-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="f852b-106">Sie müssen angeben, um den Parameter als Verweis zu übergeben, \<und das out ()-> Attribut anwenden, um einen Ausgabeparameter darzustellen, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f852b-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="f852b-107">Ausführlichere Informationen finden Sie in der-Version [SQL Server Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="f852b-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="f852b-108">**Dokumentation zu SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f852b-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="f852b-109">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f852b-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="f852b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f852b-110">See also</span></span>

- <span data-ttu-id="f852b-111">[Erstellen von SQL Server 2005-Objekten in verwaltetem Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f852b-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="f852b-112">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f852b-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
