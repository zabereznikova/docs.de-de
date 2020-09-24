---
title: SQL Server Compact und LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 7963db9e05eca7a7a148228c6d2fbca0221ca870
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155678"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact und LINQ to SQL

SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert wird. Weitere Informationen finden Sie unter [Verwenden von SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 In diesem Thema werden die Hauptunterschiede in der Verwendung, Konfiguration, den Featuresätzen und dem Umfang der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Unterstützung erläutert.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL  

 Standardmäßig ist SQL Server Compact für alle Visual Studio-Editionen installiert und auf dem Entwicklungs Computer zur Verwendung mit verfügbar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . Die Bereitstellung einer Anwendung, die SQL Server Compact verwendet, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterscheidet sich jedoch von der Bereitstellung für eine SQL Server Anwendung. SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.  
  
 Beachten Sie die folgenden Eigenschaften:  
  
- SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.  
  
- SQL Server Compact wird in demselben Prozess wie die Clientanwendung ausgeführt. Die Effizienz der Kommunikation mit SQL Server Compact kann daher deutlich höher sein als die Kommunikation mit SQL Server. Andererseits erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code (was mit den entsprechenden Kosten verbunden ist).  
  
- Die SQL Server Compact-DLL weist eine geringe Größe auf. Diese Funktion verringert die Gesamtgröße der Anwendung.  
  
- Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.  
  
- Der objektrelationaler Designer unterstützt SQL Server Compact nicht.  
  
## <a name="feature-set"></a>Funktionsgruppe  

 Die SQL Server Compact Featuregruppe ist in den folgenden Punkten, die sich auf Anwendungen auswirken können, viel einfacher als die Funktionsgruppe von SQL Server [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] :  
  
- SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.  
  
- SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.  
  
- SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.  
  
- SQL Server Compact bietet nur einen minimalen Optimierer. Es ist möglich, dass es bei einigen Abfragen zu Zeitüberschreitungen kommt.  
  
- SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verweis](reference.md)
