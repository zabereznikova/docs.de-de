---
title: ByteStream-Encoder
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: cbd4110ecc04923b79d6b910fcf7ab4ca2012680
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855451"
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Datei ByteStreamHttpBinding.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Mit der rechten Maustaste in des Projekts im Projektmappen-Explorer, und wählen Sie eine neue Instanz des ByteStreamHttpBindingServer-Projekts zunächst **Debuggen**, und klicken Sie dann **neue Instanz starten** aus dem Kontextmenü.  
  
3.  Mit der rechten Maustaste in des Projekts im Projektmappen-Explorer, und wählen Sie eine neue Instanz des ByteStreamHttpBindingClient-Projekts zunächst **Debuggen**, **neue Instanz starten** aus dem Kontextmenü.
