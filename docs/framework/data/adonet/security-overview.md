---
title: "Sicherheit im Überblick2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33e09965-61d5-48cc-9e8c-3b047cc4f194
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d7288eeffeb642d1e897e11153802633d71747bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="security-overview"></a>Übersicht über die Sicherheit
Die Gewährleistung der Sicherheit einer Anwendung ist ein fortwährender Prozess. Es wird niemals die Situation eintreten, dass ein Entwickler dafür garantieren kann, dass eine Anwendung vor allen Angriffen sicher ist, weil unmöglich vorhergesagt werden kann, welche Arten von Angriffen durch neue Technologien hervorgebracht werden. Umgekehrt kann nicht behauptet werden, dass Sicherheitsmängel nicht vorhanden sind oder nicht vorhanden sein können, nur weil diese noch nicht in einem System entdeckt (oder veröffentlicht) wurden. Sie müssen die Sicherheit bereits in der Entwurfsphase des Projekts planen, und Sie müssen planen, wie die Sicherheit über die gesamte Lebensdauer der Anwendung hinweg gewährleistet werden soll.  
  
## <a name="design-for-security"></a>Entwerfen von sicheren Anwendungen  
 Eines der größten Probleme bei der Entwicklung sicherer Anwendungen besteht darin, dass Sicherheit oft als etwas betrachtet wird, das erst implementiert werden muss, wenn der Code eines Projekts bereits fertiggestellt ist. Wenn die Sicherheit aber nicht von Anfang an in eine Anwendung eingebaut wird, entstehen unsichere Anwendungen, bei denen dem Aspekt der Anwendungssicherheit nicht genügend Beachtung geschenkt wurde.  
  
 Wenn Sicherheit erst kurz vor Schluss implementiert wird, führt dies zu noch mehr Fehlern, weil die Software unter den neuen Einschränkungen abbricht oder umgeschrieben werden muss, um bisher nicht vorgesehene Funktionen noch unterzubringen. Jede Zeile überarbeiteten Codes birgt die Möglichkeit, dass sich dort ein neuer Bug einschleicht. Aus diesem Grund sollten Sie Sicherheitsaspekte schon in einem frühen Entwicklungsstadium bedenken, sodass diese gemeinsam mit den neuen Funktionen entwickelt werden.  
  
### <a name="threat-modeling"></a>Erstellen von Gefahrenmodellen  
 Sie können ein System nur vor Angriffen schützen, wenn Ihnen alle potenziellen Angriffe bekannt sind, denen es ausgesetzt sein kann. Der Vorgang Sicherheitsrisiken wird *Erstellung von Bedrohungsmodellen*, ist erforderlich, die Wahrscheinlichkeit und Auswirkungen von sicherheitsverletzungen in Ihrer ADO.NET-Anwendung zu ermitteln.  
  
 Das Erstellen von Gefahrenmodellen besteht ganz allgemein aus den folgenden drei Schritten: Begreifen der Sichtweise der Gegenseite, Charakterisieren der Sicherheit des Systems und Bestimmen der Gefahren.  
  
 Das Erstellen von Gefahrenmodellen ist eine iterative Herangehensweise an die Bewertung von Sicherheitsrisiken in Ihrer Anwendung, bei der die gefährlichsten Sicherheitsrisiken herausgefunden werden sollen, also diejenigen, bei denen die Gefahr besteht, dass die Daten mit der höchsten Sicherheitsrelevanz in die falschen Hände gelangen. Nachdem Sie die Sicherheitsrisiken identifiziert haben, können Sie sie nach dem jeweiligen Risikograd sortieren und nach Priorität geordnete Gegenmaßnahmen einleiten.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|Die [Gefahrenmodellierung](http://go.microsoft.com/fwlink/?LinkId=98353) Standort auf der MSDN Security Developer Center|Die Ressourcen auf dieser Seite helfen Ihnen, den Prozess der Erstellung von Gefahrenmodellen besser zu verstehen und Gefahrenmodelle zu entwickeln, die Sie zum Absichern Ihrer eigenen Anwendungen verwenden können.|  
  
## <a name="the-principle-of-least-privilege"></a>Das Prinzip der minimalen Rechtegewährung  
 Beim Entwickeln, Erstellen und Bereitstellen Ihrer Anwendung muss davon ausgegangen werden, dass Ihre Anwendung angegriffen werden wird. Häufig gehen solche Angriffe von bösartigem Code aus, der mit den Berechtigungen des Benutzers ausgeführt wird, der die Codeausführung gestartet hat. Ein Angriff kann aber auch über eigentlich nicht bösartigen Code ausgeführt werden, der vom Angreifer per Exploit ausgenutzt wird. Gehen Sie beim Planen der Sicherheit immer vom schlimmsten Fall aus.  
  
 Eine Gegenmaßnahme besteht darin zu versuchen, so viele Mauern wie möglich um Ihren Code zu errichten, indem der Code mit minimalen Berechtigungen ausgeführt wird. Das Prinzip der minimalen Rechtegewährung besagt, dass jede Berechtigung, die gewährt wird, nur für den geringstmöglichen Teil des Codes und nur für die geringstmögliche Zeit erteilt werden sollte, der bzw. die zur Erledigung der Aufgabe unbedingt notwendig ist.  
  
 Beim Erstellen sicherer Anwendungen hat es sich bewährt, zunächst ganz ohne Berechtigungen zu beginnen und erst dann die geringstmöglichen Berechtigungen für die konkrete auszuführende Aufgabe hinzuzufügen. Wenn man damit beginnt, zunächst alle Berechtigungen zu gewähren und dann nur einzelne Berechtigungen wieder entzieht, entstehen unsichere Anwendungen, die schwierig zu testen und zu verwalten sind, weil sich aus dem ungewollten Gewähren zu vieler Rechte Sicherheitslücken ergeben können.  
  
 Weitere Informationen zum Absichern Ihrer Anwendungen finden Sie in den folgenden Ressourcen:  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Sichern von Anwendungen](/visualstudio/ide/securing-applications)|Enthält Links zu allgemeinen Sicherheitsthemen. Außerdem finden Sie hier Links zu Themen, in denen das Absichern von verteilten Anwendungen, Webanwendungen, mobilen Anwendungen und Desktopanwendungen beschrieben wird.|  
  
## <a name="code-access-security-cas"></a>Codezugriffssicherheit (Code Access Security, CAS)  
 Die Codezugriffssicherheit (Code Access Security, CAS) ist ein Mechanismus, mit dem der Zugriff von Code auf geschützte Ressourcen und Operationen beschränkt werden kann. In .NET Framework erfüllt CAS die folgenden Funktionen:  
  
-   Definieren von Berechtigungen und Berechtigungssätzen, die den Zugriff auf die verschiedenen Systemressourcen regeln  
  
-   Bereitstellen von Möglichkeiten für Administratoren, durch Verknüpfen von Berechtigungssätzen mit Codegruppen eine Sicherheitsrichtlinie zu konfigurieren  
  
-   Bereitstellen von Möglichkeiten für Code, die für die Ausführung erforderlichen sowie die erwünschten Berechtigungen anzufordern, und Festlegen, welche Berechtigungen der Code niemals haben darf  
  
-   Erteilen von Berechtigungen für jede geladene Assembly auf der Grundlage der vom Code angeforderten Berechtigungen und der laut Sicherheitsrichtlinie zulässigen Operationen  
  
-   Bereitstellen der Möglichkeit für Code festzulegen, dass seine Aufrufer bestimmte Berechtigungen haben müssen  
  
-   Bereitstellen der Möglichkeit für Code festzulegen, dass seine Aufrufer eine digitale Signatur besitzen müssen, sodass der geschützte Code nur von Aufrufern eines bestimmten Unternehmens oder eines bestimmten Standorts aufgerufen werden kann  
  
-   Durchsetzen von Einschränkungen für Code zur Laufzeit, indem die erteilten Berechtigungen der einzelnen Aufrufer in der Aufrufliste mit den Berechtigungen verglichen werden, die sie besitzen müssen  
  
 Um im Falle eines erfolgreichen Angriffs den Schaden so gering wie möglich zu halten, sollten Sie für Ihren Code einen Sicherheitskontext wählen, der nur den Zugriff auf die Ressourcen gewährt, die zum Arbeiten wirklich benötigt werden.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Codezugriffssicherheit und ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)|Beschreibt die Interaktionen zwischen der Codezugriffssicherheit, der rollenbasierten Sicherheit und teilweise vertrauenswürdigen Umgebungen aus der Sicht einer ADO.NET-Anwendung.|  
|[Codezugriffssicherheit](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|Enthält Links zu weiteren Themen mit Erläuterungen zu CAS in .NET Framework.|  
  
## <a name="database-security"></a>Datenbanksicherheit  
 Das Prinzip der minimalen Rechtegewährung gilt auch für Ihre Datenquelle. Bei der Datenbanksicherheit gilt es folgende allgemeine Richtlinien zu beachten:  
  
-   Gewähren Sie neu erstellten Konten nur die geringstmöglichen Zugriffsrechte.  
  
-   Erlauben Sie den Benutzern nicht, auf administrative Konten zuzugreifen, um den Code funktionsfähig zu bekommen.  
  
-   Geben Sie keine serverseitigen Fehlermeldungen an Clientanwendungen zurück.  
  
-   Validieren Sie sowohl auf dem Client als auch auf dem Server alle Eingaben.  
  
-   Verwenden Sie parametrisierte Befehle, und vermeiden Sie dynamische SQL-Anweisungen.  
  
-   Aktivieren Sie die Sicherheitsüberwachung und -protokollierung für die von Ihnen verwendete Datenbank, sodass Sie bei Sicherheitsverletzungen entsprechend benachrichtigt werden.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[SQL Server Security (SQL Server-Sicherheit)](../../../../docs/framework/data/adonet/sql/sql-server-security.md)|Bietet eine Übersicht über die SQL Server-Sicherheit mit Anwendungsszenarien, die wertvolle Hinweise zur Erstellung sicherer ADO.NET-Anwendungen geben, die auf SQL Server zugreifen.|  
|[Empfehlungen für die Daten für Zugriffsmethoden](http://msdn.microsoft.com/en-us/72411f32-d12a-4de8-b961-e54fca7faaf5)|Enthält Empfehlungen für das Zugreifen auf Daten und das Ausführen von Datenbankoperationen.|  
  
## <a name="security-policy-and-administration"></a>Sicherheitsrichtlinie und Verwaltung  
 Eine unsachgemäße Verwaltung der CAS-Richtlinie kann potenziell die Sicherheit schwächen. Nach dem Bereitstellen einer Anwendung sollten Verfahren zum Überwachen der Sicherheit eingesetzt und regelmäßige Risikobewertungen vorgenommen werden.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[NIB: Sicherheitsrichtlinienverwaltung](http://msdn.microsoft.com/en-us/d754e05d-29dc-4d3a-a2c2-95eaaf1b82b9)|Enthält Informationen zum Erstellen und Verwalten einer Sicherheitsrichtlinie.|  
|[NIB: Security Policy Best Practices](http://msdn.microsoft.com/en-us/d49bc4d5-efb7-4caa-a2fe-e4d3cec63c05)|Enthält Links zu Themen, in denen die Verwaltung einer Sicherheitsrichtlinie beschrieben wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [PAVE Security in Native and .NET Framework Code (PAVE-Sicherheit in nativem und .NET Framework-Code)](http://msdn.microsoft.com/en-us/bd61be84-c143-409a-a75a-44253724f784)  
 [SQL Server Security (SQL Server-Sicherheit)](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
