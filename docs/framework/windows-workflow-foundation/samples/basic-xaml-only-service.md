---
title: Einfacher nur XAML-fähiger Dienst
ms.date: 03/30/2017
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
ms.openlocfilehash: f4f296a97b9c3093874c5ec8e05023e84b0af44a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649314"
---
# <a name="basic-xaml-only-service"></a>Einfacher nur XAML-fähiger Dienst
In diesem Beispiel wird veranschaulicht, wie ein nur XAML-fähiger Dienst erstellt wird. Das Szenario ist ein Diagnosedienst für Probleme bei Fahrzeugen. Der Dienst wird als Workflow implementiert, der dem Client eine Reihe von Fragen stellt, um das Problem zu diagnostizieren. Es gibt zwei Arten von Problemen, die der Dienst diagnostizieren kann (Auto startet nicht oder Klimaanlage funktioniert nicht). Der Workflow macht mithilfe der Anforderungs-/Antwortvorlage aus dem Designer drei einfache Dienstvorgänge verfügbar. Der Dienst wird in IIS gehostet, indem ein virtuelles Verzeichnis in IIS erstellt und die Dateien service1.xamlx und Web.config in das virtuelle Verzeichnis kopiert werden. Es ist kein kompilierter Code erforderlich. Standardmäßig in diesem Beispiel kopiert automatisch die erforderlichen Dateien in das virtuelle Verzeichnis erstellt, wenn Sie die setupanweisungen für die WCF und WF-Beispiele folgen: [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) Wenn in der Visual Studio 2010 erstellt.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie die unter "[Projektmappenbasisverzeichnis] \Client\bin\debug" generierte Clientanwendung aus.  
  
3.  Die Anwendung druckt Optionen aus und aktiviert eine Option. Die Anwendung stellt dann einige Fragen; beantworten Sie diese (mithilfe der J/N-Tasten) mit Ja oder Nein. Wenn der Dienst mit der Diagnose der Probleme fertig ist, druckt die Anwendung eine Diagnose aus.  
  
4.  Die Anwendung wechselt zu den Optionen zurück. Sie können ein anderes Problem diagnostizieren oder die Anwendung beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`