---
title: "Hosten in einer verwalteten Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Hosten in einer verwalteten Anwendung
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste können in jeder [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Anwendung gehostet werden. Die Selbsthosting\-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Sie ist jedoch auch die am wenigsten robuste Hostingoption, weil verwaltete Anwendungen nicht die erweiterten Hosting\- und Verwaltungsfunktionen bereitstellen wie die anderen Hostingoptionen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], z.&\#160;B. Internetinformationsdienste \(IIS\) und Windows\-Dienste.  
  
 Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Gewusst wie: Hosten eines WCF\-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Ein ausführliches Beispiel für die Definition eines Vertrags, die Implementierung des Vertrags und das Hosting eines Dienstes innerhalb einer verwalteten Anwendung finden Sie unter [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md) und [Selbst gehostete Dienste](../../../../docs/framework/wcf/samples/self-host.md).  
  
 In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.  
  
## Konsolenanwendungen  
 Allgemeine, für das Selbsthosting geeignete Szenarien sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste, die in Konsolenanwendungen ausgeführt werden. Das Hosten eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts in einer Konsolenanwendung ist in der Regel während der Entwicklungsphase der Anwendung nützlich. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.  
  
## Rich Client\-Anwendungen  
 Andere, für das Selbsthosting geeignete allgemeine Szenarien sind Rich&\#160;Client\-Anwendungen wie jene, die auf [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] oder Windows&\#160;Forms \(WinForms\) basieren. Diese Hostingoption erleichtert es Rich&\#160;Client\-Anwendungen, wie [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]\- und WinForms\-Anwendungen, mit der Außenwelt zu kommunizieren. Ein Beispiel dafür ist ein Peer\-to\-Peer\-Kollaborationsclient, der [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] als Benutzeroberfläche nutzt und darüber hinaus als Host für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst fungiert, der es anderen Clients ermöglicht, eine Verbindung mit ihm herzustellen und Daten auszutauschen.  
  
## Siehe auch  
 [Hosting\-Dienste](../../../../docs/framework/wcf/hosting-services.md)   
 [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md)