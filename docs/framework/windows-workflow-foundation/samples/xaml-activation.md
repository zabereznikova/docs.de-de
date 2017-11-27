---
title: XAML-Aktivierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f513b10c84de968d5a18b800037b512aad90399e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-activation"></a>XAML-Aktivierung
In diesem Beispiel wird veranschaulicht, wie ein deklarativer Workflow in IIS gehostet wird. Das Beispiel umfasst den grundlegenden Workflow `EchoService` mit einem Vorgang.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf, und laden Sie alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Beispiele und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Beispiele herunter. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Projektmappe "XAMLActivation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe durch Drücken von **F5**.  
  
3.  Führen Sie WcfTestClient.exe aus. Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
    1.  cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  Führen Sie WcfTestClient.exe aus.  
  
4.  Legen Sie die Adresse des Diensts auf "WcfTestClient.exe" fest, indem Sie STRG+UMSCHALT+A drücken und die Dienstadresse auf "http://localhost:56133/Service.xamlx" setzen.  
  
5.  Führen Sie den Echo-Vorgang aus, um den Dienst zu testen.  
  
6.  Stellen Sie den Dienst in IIS mithilfe von DeployToIIS.Bat an einer Eingabeaufforderung mit Administratorrechten bereit.  
  
7.  Aktualisieren Sie die Dienstadresse auf dem Client auf "http://localhost/XAMLActivation/Service.xamlx", und testen Sie den Dienst erneut mit "WcfTestClient.exe".
