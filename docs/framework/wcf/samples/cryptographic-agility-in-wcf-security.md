---
title: Kryptografische Agilität in der WCF-Sicherheit
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714925"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Kryptografische Agilität in der WCF-Sicherheit

In diesem Beispiel wird gezeigt, wie in einem standardmäßigen/benutzerdefinierten Algorithmus angegeben wird, um eine kryptografische Agile-Implementierung in einem Windows Communication Foundation (WCF)-Client und-Dienst bereitzustellen. Das Beispiel besteht aus den folgenden Projekten:

**Dienst**

Dabei handelt es sich um einen selbst gehosteten WCF-Dienst, der die `ICalculator`-Schnittstelle implementiert und den Endpunkt mithilfe der <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter sicherer Sitzung und zuverlässiger Sitzung sichert. Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.

**Client**

Dies ist ein WCF-Client, der nach erfolgreicher Authentifizierung auf den Dienst zugreift. Er ruft die Vorgänge auf, die von der `ICalculator`-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden. Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.

## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Projekt Mappe cryptoagilität. sln in Visual Studio 2012.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Öffnen Sie den Datei-Explorer, navigieren Sie zum Verzeichnis \wcf\basic\security\cryptoagility\service\bin, und führen Sie die Datei Service. exe mit Administratorrechten aus, indem Sie mit der rechten Maustaste auf Service. exe klicken und **als Administrator ausführen**auswählen.

4. Navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Client\bin, und führen Sie die CLIENT.EXE-Datei wie gewohnt aus.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>Siehe auch

- [Windows Communication Foundation Sicherheit](../feature-details/security.md)
