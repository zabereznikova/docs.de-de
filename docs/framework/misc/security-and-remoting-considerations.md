---
title: Überlegungen zu Sicherheit und Remoting
ms.date: 03/30/2017
helpviewer_keywords:
- code security, remoting
- remoting, security
- security [.NET Framework], remoting
- secure coding, remoting
ms.assetid: 125d2ab8-55a4-4e5f-af36-a7d401a37ab0
ms.openlocfilehash: 7a56c9894da88382f40dcd475e89776a83a59322
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215783"
---
# <a name="security-and-remoting-considerations"></a>Überlegungen zu Sicherheit und Remoting
Remoting ermöglicht Ihnen das Einrichten transparenter Aufrufe zwischen Anwendungsdomänen, Prozessen oder Computern. Der Sicherheitsstack für den Codezugriff kann jedoch Prozess- oder Computergrenzen nicht überschreiten (dies gilt zwischen Anwendungsdomänen des gleichen Prozesses).  
  
 Jede remotefähige Klasse (abgeleitet von einer <xref:System.MarshalByRefObject>-Klasse) muss die Verantwortung für die Sicherheit übernehmen. Der Code sollte entweder nur in geschlossenen Umgebungen verwendet werden, in denen der aufrufende Code implizit vertrauenswürdig ist, oder Remoteaufrufe sollten so entworfen werden, dass kein geschützter Code für externe Eingaben in ggf. böswilliger Absicht verwendet werden kann.  
  
 Im Allgemeinen sollten Sie nie Methoden, Eigenschaften oder Ereignisse verfügbar machen, die durch deklarative [LinkDemand](link-demands.md) und <xref:System.Security.Permissions.SecurityAction.InheritanceDemand> Sicherheitsüberprüfungen geschützt werden. Mit Remoting werden diese Überprüfungen nicht erzwungen. Andere Sicherheitsüberprüfungen (z. b. <xref:System.Security.Permissions.SecurityAction.Demand>, [Assert](using-the-assert-method.md)usw.) funktionieren zwischen Anwendungs Domänen innerhalb eines Prozesses, funktionieren jedoch nicht in prozessübergreifenden oder Computer übergreifenden Szenarien.  
  
## <a name="protected-objects"></a>Geschützte Objekte  
 Einige Objekte enthalten Ihren Sicherheitszustand in sich. Diese Objekte sollten nicht an nicht vertrauenswürdigen Code übergeben werden, der dann eine über seine eigenen Berechtigungen hinausgehende Sicherheitsautorisierung erhalten würde.  
  
 Ein Beispiel ist das Erstellen eines <xref:System.IO.FileStream>-Objekts. Die <xref:System.Security.Permissions.FileIOPermission> wird zum Zeitpunkt der Erstellung angefordert, und bei Erfolg wird das Dateiobjekt zurückgegeben. Wenn dieser Objektverweis jedoch an Code ohne Dateiberechtigungen übergeben wird, ist das Objekt in der Lage, diese Datei zu lesen und in sie zu schreiben.  
  
 Die einfachste Verteidigung für ein solches Objekt besteht darin, **die gleiche "** " "" "" "" "".  
  
## <a name="application-domain-crossing-issues"></a>Probleme beim anwendungsdomänenübergreifenden Zugriff  
 Zum Isolieren von Code in verwalteten Hostingumgebungen ist es üblich, mehrere untergeordnete Anwendungsdomänen mit einer expliziten Richtlinie zu generieren, um die Berechtigungsstufen verschiedener Assemblys zu verringern. In der Standardanwendungsdomäne bleibt die Richtlinie für diese Assemblys jedoch unverändert. Wenn eine der untergeordneten Anwendungsdomänen die Standardanwendungsdomäne zum Laden einer Assembly zwingen kann, gehen die Auswirkungen der Codeisolierung verloren, und Typen in der erzwungen geladenen Assembly können Code auf einer höheren Vertrauensebene ausführen.  
  
 Eine Anwendungsdomäne kann eine andere Anwendungsdomäne zum Laden einer Assembly und Ausführen von darin enthaltenem Code durch Aufrufen eines Proxys für ein Objekt zwingen, das in der anderen Anwendungsdomäne gehostet wird. Zum Abrufen eines anwendungsübergreifenden Domänenproxys muss die Anwendungsdomäne, die das Objekt hostet, diesen über einen Methodenaufrufparameter oder Rückgabewert verteilen. Wenn die Anwendungsdomäne soeben erstellt wurde, verfügt der Ersteller für das <xref:System.AppDomain>-Objekt standardmäßig über einen Proxy. Damit vermieden wird, dass die Codeisolierung verletzt wird, sollte eine Anwendungsdomäne mit einer höheren Vertrauensebene daher keine Verweise auf durch Verweis gemarshallte Objekte (Instanzen von Klassen, die von <xref:System.MarshalByRefObject> abgeleitet sind) in der eigenen Domäne an Anwendungsdomänen mit niedrigeren Vertrauensebenen verteilen.  
  
 In der Regel erstellt die Standardanwendungsdomäne die untergeordneten Anwendungsdomänen mit jeweils einem Steuerelementobjekt. Das Steuerelementobjekt verwaltet die neue Anwendungsdomäne und nimmt gelegentlich Anweisungen von der Standardanwendungsdomäne entgegen, kann aber nicht direkt Kontakt mit der Domäne aufnehmen. Gelegentlich ruft die Standardanwendungsdomäne Ihren Proxy für das Steuerelementobjekt auf. Es können jedoch Fälle auftreten, in denen es erforderlich ist, dass das Steuerelementobjekt einen Rückruf an die Standardanwendungsdomäne ausgibt. In diesen Fällen übergibt die Standardanwendungsdomäne ein durch Verweis gemarshalltes Rückrufobjekt an den Konstruktor des Steuerelementobjekts. Es liegt in der Verantwortung des Steuerelementobjekts, diesen Proxy zu schützen. Würde das Steuerelementobjekt den Proxy in einem öffentlichen statischen Feld einer öffentlichen Klasse positionieren oder den Proxy auf andere Weise öffentlich bereitstellen, würde dies einen gefährlichen Mechanismus für anderen Code eröffnen, einen Rückruf in die Standardanwendungsdomäne auszugeben. Aus diesem Grund sind Steuerelementobjekte immer implizit vertrauenswürdig, damit der Proxy privat bleibt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
