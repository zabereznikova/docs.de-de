---
title: Konfigurationskanalfactory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 1f95356b0b473b297b36c7661c849589e9c0d6ef
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483735"
---
# <a name="configuration-channel-factory"></a>Konfigurationskanalfactory
In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> behandelt. Die <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> ermöglicht die zentrale Verwaltung der WCF-Client-Konfiguration. Dies kann auch in Szenarien nützlich sein, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.  
  
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
  
4.  Verschieben der **Service** Projekt am Anfang der Liste mit der **Aktion "Start"**, und verschieben Sie dann die **Client** nach dem Projekt die **Service**-Projekt auch mit der **Aktion "Start"**, sodass die **Client** Projekt ausgeführt wird, nachdem die **Service** Projekt.  
  
5.  Klicken Sie auf **OK**, und drücken Sie dann F5 (oder STRG + F5), um das Beispiel auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
