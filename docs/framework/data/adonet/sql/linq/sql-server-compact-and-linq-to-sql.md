---
title: SQL Server Compact und LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: a0cb45b31f7134264068297f54013f49b35f669d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651202"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact und LINQ to SQL
SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert. Weitere Informationen finden Sie unter [mithilfe von SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 In diesem Thema wird beschrieben, die wichtigsten Unterschiede in Verwendung, Konfiguration, Funktionsgruppen und Rahmen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützen.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL  
 Standardmäßig SQL Server Compact wird für alle Editionen von Visual Studio installiert und steht daher auf dem Entwicklungscomputer zur Verwendung mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Aber die Bereitstellung einer Anwendung, die SQL Server Compact verwendet und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterscheidet sich von dem für eine SQL Server-Anwendung. SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.  
  
 Beachten Sie die folgenden Eigenschaften:  
  
- SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.  
  
- SQL Server Compact im selben Prozess wie die Clientanwendung ausgeführt wird. Die Effizienz der Kommunikation mit SQL Server Compact kann deshalb bedeutend höher als die Kommunikation mit SQL Server sein. Andererseits, erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code mit den entsprechenden Kosten verbunden.  
  
- Die Größe der SQL Server Compact-DLL ist klein. Diese Funktion verringert die Gesamtgröße der Anwendung.  
  
- Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.  
  
- Der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] bietet keine Unterstützung für SQL Server Compact.  
  
## <a name="feature-set"></a>Funktionsgruppe  
 Der SQL Server Compact-Funktionsgruppe ist viel einfacher als die Funktionsgruppe von SQL Server auf folgende Weise, die beeinflussen können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen:  
  
- SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.  
  
- SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.  
  
- SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.  
  
- SQL Server Compact bietet nur einen minimalen Optimierer. Es ist möglich, dass einige Abfragen zu zeitüberschreitungen kommt.  
  
- SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.  
  
## <a name="see-also"></a>Siehe auch

- [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
