---
title: SQL Server Compact und LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: b5a1a12018bd85cf313c1841e6b67ab2edf67b4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792532"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact und LINQ to SQL
SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert wird. Weitere Informationen finden Sie unter [Verwenden von SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 In diesem Thema werden die Hauptunterschiede in der Verwendung, Konfiguration, den Featuresätzen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Umfang der Unterstützung erläutert.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL  
 Standardmäßig ist SQL Server Compact für alle Visual Studio-Editionen installiert und auf dem Entwicklungs Computer zur Verwendung mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]verfügbar. Die Bereitstellung einer Anwendung, die SQL Server Compact [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet, unterscheidet sich jedoch von der Bereitstellung für eine SQL Server Anwendung. SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.  
  
 Beachten Sie die folgenden Eigenschaften:  
  
- SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.  
  
- SQL Server Compact wird in demselben Prozess wie die Client Anwendung ausgeführt. Die Effizienz der Kommunikation mit SQL Server Compact kann daher deutlich höher sein als die Kommunikation mit SQL Server. SQL Server Compact hingegen erfordert Interoperabilität zwischen verwaltetem und nicht verwaltetem Code und den zugehörigen Kosten.  
  
- Die Größe der SQL Server Compact dll ist klein. Diese Funktion verringert die Gesamtgröße der Anwendung.  
  
- Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.  
  
- Der objektrelationaler Designer unterstützt SQL Server Compact nicht.  
  
## <a name="feature-set"></a>Funktionsgruppe  
 Die SQL Server Compact Featuregruppe ist in den folgenden Punkten, die sich auf Anwendungen auswirken [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] können, viel einfacher als die Funktionsgruppe von SQL Server:  
  
- SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.  
  
- SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.  
  
- SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.  
  
- SQL Server Compact bietet nur einen minimalen Optimierer. Möglicherweise kommt es bei einigen Abfragen zu einem Timeout.  
  
- SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.  
  
## <a name="see-also"></a>Siehe auch

- [Verweis](reference.md)
