---
title: CLR-gespeicherte Prozeduren
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 736020695ae40a8884057ddee8aac8abe6e8c1fd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554194"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="b9b17-102">CLR-gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b9b17-102">CLR Stored Procedures</span></span>
<span data-ttu-id="b9b17-103">Gespeicherte Prozeduren sind Routinen, die nicht in Skalarausdrücken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b9b17-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="b9b17-104">Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b9b17-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9b17-105">Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b9b17-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="b9b17-106">Sie müssen angeben, um den Parameter als Verweis zu übergeben, und das- \<Out()> Attribut auf die Darstellung eines Ausgabe Parameters anwenden, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b9b17-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="b9b17-107">Ausführlichere Informationen finden Sie in der-Version [SQL Server Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9b17-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="b9b17-108">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="b9b17-108">**SQL Server documentation**</span></span>

1. <span data-ttu-id="b9b17-109">[CLR-gespeicherte Prozeduren](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="b9b17-109">[CLR Stored Procedures](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b17-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9b17-110">See also</span></span>

- <span data-ttu-id="b9b17-111">[Erstellen von SQL Server 2005-Objekten in verwaltetem Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b9b17-111">[Creating SQL Server 2005 Objects In Managed Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="b9b17-112">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9b17-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
