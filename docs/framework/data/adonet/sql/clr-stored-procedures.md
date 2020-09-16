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
# <a name="clr-stored-procedures"></a>CLR-gespeicherte Prozeduren
Gespeicherte Prozeduren sind Routinen, die nicht in Skalarausdrücken verwendet werden können. Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.  
  
> [!NOTE]
> Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#. Sie müssen angeben, um den Parameter als Verweis zu übergeben, und das- \<Out()> Attribut auf die Darstellung eines Ausgabe Parameters anwenden, wie im folgenden dargestellt:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Ausführlichere Informationen finden Sie in der-Version [SQL Server Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.
  
 **SQL Server-Dokumentation**

1. [CLR-gespeicherte Prozeduren](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von SQL Server 2005-Objekten in verwaltetem Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Übersicht über ADO.NET](../ado-net-overview.md)
