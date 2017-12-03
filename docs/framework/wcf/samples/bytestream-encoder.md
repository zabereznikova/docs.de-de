---
title: ByteStream-Encoder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7663e0c0073110c0df2e3ece20c240af46a61e92
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="bytestream-encoder"></a>ByteStream-Encoder
In diesem Beispiel wird veranschaulicht, wie eine `ByteStreamHttpBinding` erstellt wird, eine <xref:System.ServiceModel.Channels.Binding>, die die Funktionalität des Bytestreamencoder veranschaulicht.  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird veranschaulicht, wie eine Standard-<xref:System.ServiceModel.Channels.Binding> mithilfe der Standardbindungselemente <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.HttpTransportBindingElement> erstellt wird. In diesem Beispiel wird gezeigt, wie mit dem Bytestreamencoder ein Bild hochgeladen und heruntergeladen wird. Die Bytedatenstromencoder-Funktion unterstützt nur den HTTP-Transport und bietet keine Unterstützung von Funktionen wie zuverlässiges Messaging oder Sicherheit. Die einzige unterstützte <xref:System.ServiceModel.Channels.MessageVersion> ist <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
> [!IMPORTANT]
>  Wenn Sie dieses Beispiel mit [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] oder unter [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)] ausführen, stellen Sie sicher, dass Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] mit erweiterten Berechtigungen ausführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Datei ByteStreamHttpBinding.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Starten Sie eine neue Instanz des ByteStreamHttpBindingServer-Projekts, indem Sie das Projekt im Projektmappen-Explorer mit der rechten Maustaste und auswählen **Debuggen**, und klicken Sie dann **neue Instanz starten** aus dem Kontextmenü.  
  
3.  Starten Sie eine neue Instanz des ByteStreamHttpBindingClient-Projekts, indem Sie das Projekt im Projektmappen-Explorer mit der rechten Maustaste und auswählen **Debuggen**, **neue Instanz starten** aus dem Kontextmenü.
