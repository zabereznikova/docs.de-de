---
title: "Programmierarchitektur für Dienstanwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a>Programmierarchitektur für Dienstanwendungen
Windows-dienstanwendungen basieren auf einer Klasse, die von erben die <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> Klasse. Sie überschreiben die Methoden, die von dieser Klasse und Funktionen sind, um zu bestimmen, wie das Verhalten des Diensts definiert.  
  
 Die wichtigsten Klassen diensterstellung beteiligt sind:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>– Sie überschreiben Sie Methoden aus der <xref:System.ServiceProcess.ServiceBase> Klasse beim Erstellen eines Diensts, und definieren Sie den Code, um zu bestimmen, wie Ihre Service-Funktionen in dieser Klasse geerbt.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>und <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> – verwenden Sie diese Klassen zum Installieren und deinstallieren den Dienst.  
  
 Darüber hinaus eine Klasse mit dem Namen <xref:System.ServiceProcess.ServiceController> können verwendet werden, um den Dienst selbst bearbeiten. Diese Klasse ist nicht zur Erstellung eines Diensts jedoch dienen zum Starten und beenden Sie den Dienst, Befehle an ihn übergeben und eine Reihe von Enumerationen zurück.  
  
## <a name="defining-your-services-behavior"></a>Definieren des Verhaltens des Diensts  
 In Ihrer Dienstklasse überschreiben Sie die Funktionen der Basisklasse, die bestimmen, was geschieht, wenn der Status des Diensts im Dienststeuerungs-Manager geändert wird. Die <xref:System.ServiceProcess.ServiceBase> Klasse macht die folgenden Methoden, die Sie überschreiben können, um ein benutzerdefiniertes Verhalten hinzuzufügen.  
  
|Methode|Zum Überschreiben|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Geben Sie an, welche Aktionen ausgeführt werden soll, wenn der Dienst ausgeführt wird. Sie müssen Code schreiben, in diesem Verfahren für Ihren Dienst um sinnvolle Aufgaben ausführen.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Geben Sie an, was geschehen soll, wenn der Dienst angehalten wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Geben Sie an, was geschehen soll, wenn der Dienst beendet wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Geben Sie an, was geschehen soll, wenn der Dienst wird fortgesetzt, normal funktionsfähig, nachdem er angehalten wurde.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Geben Sie an, was unmittelbar vor dem Herunterfahren, des Systems geschehen soll, wenn der Dienst zu diesem Zeitpunkt ausgeführt wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Geben Sie an, was geschehen soll, wenn der Dienst einen benutzerdefinierten Befehl empfängt. Weitere Informationen über benutzerdefinierte Befehle finden Sie unter MSDN online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Geben Sie an, wie der Dienst reagieren soll, wenn ein Verwaltungsereignis Power, z. B. eine Batterie oder angehalten empfangen wird.|  
  
> [!NOTE]
>  Diese Methoden darstellen, Status, in denen der Dienst während seiner Lebensdauer durchlaufen; der Dienst Übergänge von einem Status zum nächsten. Angenommen, Sie rufen niemals den Dienst so reagieren Sie auf eine <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> vor dem Befehl <xref:System.ServiceProcess.ServiceBase.OnStart%2A> aufgerufen wurde.  
  
 Es gibt mehrere andere Eigenschaften und Methoden, die von Interesse sind. Dazu gehören:  
  
-   Die <xref:System.ServiceProcess.ServiceBase.Run%2A> Methode für die <xref:System.ServiceProcess.ServiceBase> Klasse. Dies ist der Haupteinstiegspunkt für den Dienst. Wenn Sie einen Dienst mithilfe der Windows-Dienstvorlage erstellen, in der Anwendungsverzeichnis Code eingefügt `Main` Methode, um den Dienst auszuführen. Dieser Code sieht wie folgt:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  In diesen Beispielen verwenden ein Array vom Typ <xref:System.ServiceProcess.ServiceBase>in die jeden Dienst, der die Anwendung enthält, kann hinzugefügt werden, und klicken Sie dann alle Dienste zusammen ausgeführt werden können. Wenn Sie nur einen einzelnen Dienst erstellen, allerdings empfiehlt sich nicht auf das Array verwenden, und deklarieren Sie einfach ein neues Objekt, das erben von <xref:System.ServiceProcess.ServiceBase> und führen Sie es dann. Ein Beispiel finden Sie unter [wie: Schreiben Sie Dienste programmgesteuert](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Eine Reihe von Eigenschaften für die <xref:System.ServiceProcess.ServiceBase> Klasse. Diese bestimmen, welche Methoden für Ihren Dienst aufgerufen werden können. Beispielsweise, wenn die <xref:System.ServiceProcess.ServiceBase.CanStop%2A> -Eigenschaftensatz auf `true`, die <xref:System.ServiceProcess.ServiceBase.OnStop%2A> -Methode für Ihren Dienst aufgerufen werden kann. Wenn die <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> -Eigenschaftensatz auf `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> und <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> Methoden aufgerufen werden können. Beim Festlegen dieser Eigenschaften zu `true`, Sie sollten dann außer Kraft setzen und Verarbeitung für die zugeordneten Methoden definieren.  
  
    > [!NOTE]
    >  Der Dienst muss über mindestens überschreiben <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> um nützlich zu sein.  
  
 Sie können auch eine Komponente mit dem Namen der <xref:System.ServiceProcess.ServiceController> Kommunikation mit und das Verhalten von einem vorhandenen Dienst steuern.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)
