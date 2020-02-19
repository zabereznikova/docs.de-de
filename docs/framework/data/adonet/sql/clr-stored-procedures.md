---
title: CLR-gespeicherte Prozeduren
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: ca0fd2d33f0ad56c96fb63530e6ba3f7f7890f81
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450361"
---
# <a name="clr-stored-procedures"></a>CLR-gespeicherte Prozeduren
Gespeicherte Prozeduren sind Routinen, die nicht in Skalarausdrücken verwendet werden können. Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.  
  
> [!NOTE]
> Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#. Sie müssen angeben, um den Parameter als Verweis zu übergeben, und das \<out () > Attribut anwenden, um einen Ausgabeparameter darzustellen, wie im folgenden dargestellt:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Ausführlichere Informationen finden Sie in der-Version [SQL Server Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.
  
 **SQL Server-Dokumentation**

1. [CLR-gespeicherte Prozeduren](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von SQL Server 2005-Objekten in verwaltetem Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Übersicht über ADO.NET](../ado-net-overview.md)
