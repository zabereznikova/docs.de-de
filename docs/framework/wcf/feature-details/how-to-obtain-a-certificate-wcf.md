---
title: 'Vorgehensweise: Abrufen eines Zertifikats (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1b7ab4ed91487965ac8b0d78a9a44818cfee9eb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Vorgehensweise: Abrufen eines Zertifikats (WCF)
Rufen Sie zuerst Zertifikate ab, um die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Funktionen mit X.509-Zertifikaten zu verwenden.  
  
### <a name="to-obtain-an-x509-certificate"></a>So rufen Sie ein X.509-Zertifikat ab  
  
1.  Wählen Sie eine der folgenden Optionen aus:  
  
    -   Erwerben Sie ein Zertifikat von einer Zertifizierungsstelle, z. B. VeriSign, Inc.  
  
    -   Richten Sie einen eigenen Zertifikatdienst ein, und lassen Sie die Zertifikate von einer Zertifizierungsstelle signieren. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows&amp;#160;2000 Server, Windows&amp;#160;2000 Server Datacenter und Windows&amp;#160;2000 Datacenter Server verfügen alle über Zertifikatdienste mit Public Key Infrastructure (PKI)-Unterstützung. Verwenden Sie in Windows Server 2008 die [Active Directory Certificate Services](http://go.microsoft.com/fwlink/?LinkID=153483) Rolle um eine Zertifizierungsstelle zu verwalten.  
  
    -   Richten Sie einen eigenen Zertifikatsdienst ein, und lassen Sie die Zertifikate nicht signieren.  
  
    > [!NOTE]
    >  Unabhängig vom gewählten Ansatz muss der Empfänger der SOAP-Anforderung, die das X.509-Zertifikat enthält, dem X.509-Zertifikat vertrauen. Dies bedeutet, dass sich das X.509-Zertifikat oder ein Aussteller in der Zertifikatkette im Speicher für vertrauenswürdige Personen befindet und sich das X.509-Zertifikat nicht im Speicher für nicht vertrauenswürdige Zertifikate befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
