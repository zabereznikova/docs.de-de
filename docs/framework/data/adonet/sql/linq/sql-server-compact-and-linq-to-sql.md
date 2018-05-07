---
title: SQL Server Compact und LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 74b8a7a6dfc9a4050dbba9a8c2f6969dba42656c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact und LINQ to SQL
SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert. Weitere Informationen finden Sie unter [PAVE über mithilfe von SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 In diesem Thema werden die Hauptunterschiede hinsichtlich der Verwendung, Konfiguration, Funktionsgruppen und Umfang der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützen.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL  
 Standardmäßig SQL Server Compact wird für alle Editionen von Visual Studio installiert und steht daher auf dem Entwicklungscomputer zur Verwendung mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Aber die Bereitstellung einer Anwendung, die SQL Server Compact verwendet und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterscheidet sich von dem für eine SQL Server-Anwendung. SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.  
  
 Beachten Sie die folgenden Eigenschaften:  
  
-   SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.  
  
-   SQL Server Compact in demselben Prozess wie die Clientanwendung ausgeführt wird. Die Effizienz der Kommunikation mit SQL Server Compact kann deshalb bedeutend höher als bei der Kommunikation mit SQL Server sein. Andererseits, erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code mit den entsprechenden Kosten verbunden ist.  
  
-   Die SQL Server Compact-DLL ist klein. Diese Funktion verringert die Gesamtgröße der Anwendung.  
  
-   Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.  
  
-   Der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] bietet keine Unterstützung für SQL Server Compact.  
  
## <a name="feature-set"></a>Funktionsgruppe  
 Der SQL Server Compact-Funktionsgruppe ist erheblich einfacher als die Funktionsgruppe von SQL Server auf folgende Weise, die beeinflussen können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen:  
  
-   SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.  
  
-   SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.  
  
-   SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.  
  
-   SQL Server Compact bietet nur einen minimalen Optimierer. Es ist möglich, dass einige Abfragen zu zeitüberschreitungen.  
  
-   SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
