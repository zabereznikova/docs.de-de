---
title: Konfigurationskanalfactory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a79a5c4997403f018ba34aea65e4c9fadab29443
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-channel-factory"></a>Konfigurationskanalfactory
In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> behandelt. <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> ermöglicht die zentrale Verwaltung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientkonfiguration. Dies kann auch in Szenarien nützlich sein, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird gezeigt, wie eine bestimmte Konfigurationsdatei mit <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zu einer Clientanwendung hinzugefügt wird, ohne die standardmäßige Anwendungskonfigurationsdatei verwenden zu müssen.  
  
 Das Beispiel umfasst zwei Projekte. Das erste Projekt ist ein einfacher Dienst, der auf Nachrichten von den Clients antwortet. Das zweite Projekt ist eine Clientanwendung, die für die Konfigurationsdatei Test.config mithilfe einer <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zwei <xref:System.Configuration.ExeConfigurationFileMap>-Objekte erstellt und diese für die Kommunikation mit dem Dienst verwendet. Beide Clients verwenden die in Test.config angegebene Konfiguration für die Kommunikation mit dem Dienst.  
  
 Der folgende Code fügt einer Clientanwendung eine benutzerdefinierte Konfigurationsdatei hinzu.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] mit Administratorrechten.  
  
2.  Mit der rechten Maustaste in der Projektmappe configurationchannelfactory (2 Projekte), und wählen Sie dann **Eigenschaften**.  
  
3.  In **allgemeine Eigenschaften**Option **Startprojekt**, und klicken Sie dann auf **mehrere Startprojekte**.  
  
4.  Verschieben der **Service** Projekt am Anfang der Liste mit den **Aktion "Start"**, und verschieben Sie dann die **Client** nach dem Projekt die **Dienst**-Projekt auch mit der **Aktion "Start"**, sodass die **Client** Projekt ausgeführt, nachdem die **Service** Projekt.  
  
5.  Klicken Sie auf **OK**, und drücken Sie dann F5 (oder STRG + F5), um das Beispiel auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
