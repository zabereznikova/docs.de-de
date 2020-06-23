---
title: Net.TCP-Anschlussfreigabe
description: Erfahren Sie mehr über ein TCP-basiertes Protokoll für die Hochleistungs Kommunikation und den Dienst, der die gemeinsame Nutzung von Ports über mehrere Benutzer Prozesse in WCF hinweg ermöglicht.
ms.date: 03/30/2017
helpviewer_keywords:
- port activation [WCF]
- port sharing [WCF]
ms.assetid: f13692ee-a179-4439-ae72-50db9534eded
ms.openlocfilehash: a9579c588906f509dd835d3c9b25571495d147e0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245244"
---
# <a name="nettcp-port-sharing"></a>Net.TCP-Anschlussfreigabe
Windows Communication Foundation (WCF) stellt ein neues TCP-basiertes Netzwerkprotokoll (net. TCP://) für die leistungsstarke Kommunikation bereit. WCF führt außerdem eine neue Systemkomponente ein, den Net. TCP-Port Freigabe Dienst, mit dem net. TCP-Ports für mehrere Benutzer Prozesse freigegeben werden können.  
  
## <a name="background-and-motivation"></a>Hintergrund und Motivation  
 Als das TCP/IP-Protokoll erstmals eingeführt wurde, wurde es nur von einer geringen Anzahl von Anwendungsprotokollen verwendet. TCP/IP verwendete Anschlussnummern, um zwischen Anwendungen zu unterscheiden, indem es jedem Anwendungsprotokoll eine eindeutige 16-bit-Anschlussnummer zuwies. HTTP-Verkehr verwendet heute beispielsweise standardmäßig den TCP-Anschluss 80, SMTP verwendet den TCP-Anschluss 25, und FTP verwendet die TCP-Anschlüsse 20 und 21. Andere Anwendungen, die TCP als Transport verwenden, können eine weitere verfügbare Anschlussnummer wählen, entweder durch Konventionen oder durch formale Standardisierung.  
  
 Die Verwendung von Anschlussnummern zur Unterscheidung zwischen Anwendungen barg Sicherheitsprobleme. Firewalls sind in der Regel so konfiguriert, dass Sie TCP-Verkehr an allen Anschlüssen außer den wenigen wohlbekannten Eingangspunkten blockieren, sodass die Bereitstellung einer Anwendung, die einen Nicht-Standardanschluss verwendet, durch das Vorhandensein firmenspezifischer oder persönlicher Firewalls oft kompliziert oder sogar unmöglich ist. Anwendungen, die über bekannten, bereits zugelassene Standardanschlüsse kommunizieren können, verringern die Angriffsfläche für externe Angriffe. Viele Netzwerkanwendungen verwenden das HTTP-Protokoll, da die meisten Firewalls standardmäßig so konfiguriert sind, dass sie Verkehr am TCP-Anschluss&#160;80 zulassen.  
  
 Das HTTP.SYS-Modell, in dem der Verkehr für viele verschiedene HTTP-Anwendungen als Multiplex über einen einzelnen TCP-Anschluss geleitet wird, ist heute Standard auf der Windows-Plattform. Dies bietet Firewalladministratoren einen gemeinsamen Steuerungspunkt, und bietet zugleich Anwendungsentwicklern die Möglichkeit, die Bereitstellungskosten beim Erstellen neuer Anwendungen, die das Netzwerk verwenden können, zu minimieren.  
  
 Die Möglichkeit, Anschlüsse für mehrere HTTP-Anwendungen freizugeben ist schon lange eine Funktion von Internetinformationsdiensten (Internet Information Services, IIS). Dies war jedoch nur mit der Einführung von HTTP.SYS (dem Kernel Modus-HTTP-Protokolllistener) mit IIS 6,0, dass diese Infrastruktur vollständig generalisiert wurde. Tatsächlich ermöglicht HTTP.SYS es beliebigen Benutzerprozessen, die für HTTP-Verkehr vorgesehen TCP-Anschlüsse gemeinsam zu verwenden. Durch diese Fähigkeit können zahlreiche HTTP-Anwendungen auf dem selben physischen Gerät in getrennten, isolierten Prozessen koexistieren und dabei die zum Senden und Empfangen von Verkehr über den TCP-Anschluss 80 erforderliche Netzwerkinfrastruktur gemeinsam verwenden. Der Net.TCP-Portfreigabedienst ermöglicht die gleiche Art der Anschlussfreigabe für net.tcp-Anwendungen.  
  
## <a name="port-sharing-architecture"></a>Architektur der Anschlussfreigabe  
 Die Architektur der Port Freigabe in WCF besteht aus drei Hauptkomponenten:  
  
- Ein Arbeitsprozess: Ein beliebiger Prozess, der mithilfe freigegebener Anschlüsse über net.tcp:// kommuniziert.  
  
- Der WCF-TCP-Transport: Implementiert das net. TCP://-Protokoll.  
  
- Der Net.TCP-Portfreigabedienst: Ermöglicht mehreren Arbeitsprozessen, den gleichen TCP-Anschluss zu verwenden.  
  
 Der Net.TCP-Portfreigabedienst ist ein Windows-Dienst im Benutzermodus, der net.tcp://-Verbindungen im Namen von Arbeitsprozessen akzeptiert, die sich über ihn verbinden. Wenn eine Socketverbindung ankommt, untersucht der Portfreigabedienst den eingehenden Nachrichtenstrom, um dessen Zieladresse zu erhalten. Basierend auf dieser Adresse kann der Portfreigabedienst den Datenstrom zu der Anwendung weiterleiten, die ihn letztendlich verarbeitet.  
  
 Wenn ein WCF-Dienst, der die net. TCP://-Port Freigabe verwendet, geöffnet wird, öffnet die WCF-TCP-Transport-Infrastruktur im Anwendungsprozess nicht direkt einen TCP-Socket. Stattdessen registriert die Transportinfrastruktur den Basisadressen-URI (Uniform Resource Identifier) des Dienstes mit dem Net.TCP-Portfreigabedienst und wartet darauf, dass der Portfreigabedienst in ihrem Namen den Eingang von Nachrichten abhört.  Der Portfreigabedienst leitet an den Anwendungsdienst adressierte Nachrichten bei Eingang weiter.  
  
## <a name="installing-port-sharing"></a>Installieren der Anschlussfreigabe  
 Der net. TCP-Port Freigabe Dienst ist auf allen Betriebssystemen verfügbar, die WinFX unterstützen, der Dienst ist jedoch standardmäßig nicht aktiviert. Als Sicherheitsmaßnahme muss der Net.TCP-Portfreigabedienst vor der ersten Verwendung manuell von einem Administrator aktiviert werden. Der Net.TCP-Portfreigabedienst stellt Konfigurationsoptionen zur Verfügung, mit denen Sie einige Merkmale der dem Portfreigabedienst gehörenden Netzwerksockets ändern können. Weitere Informationen finden Sie unter Gewusst [wie: Aktivieren des net. TCP-Port Freigabe Dienstanbieter](how-to-enable-the-net-tcp-port-sharing-service.md).  
  
## <a name="using-nettcp-port-sharing-in-an-application"></a>Verwenden der Net.tcp-Anschlussfreigabe in einer Anwendung  
 Die einfachste Möglichkeit zur Verwendung von net. TCP://der Port Freigabe in der WCF-Anwendung besteht darin, einen Dienst mithilfe von verfügbar zu machen <xref:System.ServiceModel.NetTcpBinding> und dann den Net. TCP-Port Freigabe Dienst mithilfe der-Eigenschaft zu aktivieren <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> .  
  
 Weitere Informationen hierzu finden Sie unter Gewusst [wie: Konfigurieren eines WCF-Dienstanbieter für die Verwendung der Port Freigabe](how-to-configure-a-wcf-service-to-use-port-sharing.md).  
  
## <a name="security-implications-of-port-sharing"></a>Sicherheitsauswirkungen der Anschlussfreigabe  
 Obwohl der Net.TCP-Portfreigabedienst eine Verarbeitungsschicht zwischen Anwendungen und dem Netzwerk bereitstellt, sollten Anwendungen, die die Anschlussfreigabe nutzen, zusätzlich so gesichert werden, als würden sie das Netzwerk direkt überwachen. Insbesondere sollten Anwendungen, die die Anschlussfreigabe nutzen, die Prozessprivilegien auswerten, unter denen sie ausgeführt werden. Ziehen Sie in Betracht, die Anwendung unter dem integrierten Netzwerkdienstkonto auszuführen, das mit der minimalen Gruppe der zur Netzwerkkommunikation erforderlichen Privilegien ausgeführt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren des Net.TCP-Portfreigabediensts](configuring-the-net-tcp-port-sharing-service.md)
- [Hosting](hosting.md)
- [Vorgehensweise: Konfigurieren eines WCF-Diensts für die Portfreigabe](how-to-configure-a-wcf-service-to-use-port-sharing.md)
- [Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts](how-to-enable-the-net-tcp-port-sharing-service.md)
