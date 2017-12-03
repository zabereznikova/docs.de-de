---
title: Verwenden der WCF-Entwicklungstools
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9532363adafd492ca35e10e6d20c788ddf5b1d17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-wcf-development-tools"></a>Verwenden der WCF-Entwicklungstools
In diesem Abschnitt werden die [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Entwicklungstools beschrieben, mit denen Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst entwickeln können.  
  
 Sie können die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Vorlagen als Grundlage beim Erstellen Ihres eigenen Diensts verwenden und dann mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host und [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient den Dienst debuggen und testen. Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.  
  
## <a name="the-wcf-developer-tools"></a>Die WCF-Entwicklungstools  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Mithilfe der vordefinierten [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Projektvorlagen und -Elementvorlagen in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] können Sie mühelos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste und entsprechende Anwendungen erstellen.  
  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host (WcfSvcHost.exe) können Sie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Debugger (F5) starten, um automatisch einen implementierten Dienst zu hosten und zu testen. Anschließend können Sie den Dienst mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu identifizieren und zu beheben.  
  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, die Eingabe an den Dienst senden und die zurückgesendete Antwort des Diensts anzeigen können. Zusammen mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host ermöglicht er einen problemlosen Diensttest.  
  
 [Generieren von Datentypklassen aus XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden. Die in den Daten definierten Klassen werden in Codetypen konvertiert.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Verwenden der Tools ohne Administratorberechtigung  
 Damit auch Benutzer ohne Administratorberechtigung [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste entwickeln können, wird während der Installation von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eine ACL (Access Control List) für den Namespace "http://+:8731/Design_Time_Addresses" erstellt. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen. Darüber hinaus haben Benutzer die Möglichkeit, den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne dass ihnen Administratorberechtigungen zugewiesen werden müssen.  
  
 Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Netsh.exe, finden Sie unter [wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
