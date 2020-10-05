---
title: Programmierarchitektur für Dienstanwendungen
description: Hier erfahren Sie mehr über die Programmierarchitektur für Dienstanwendungen. Windows-Dienstanwendungen basieren auf einer Klasse, die von System.ServiceProcess.ServiceBase erbt.
ms.date: 03/30/2017
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
ms.openlocfilehash: 386311228abb08600acc249e80702c724c137900
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609264"
---
# <a name="service-application-programming-architecture"></a>Programmierarchitektur für Dienstanwendungen
Windows-Dienstanwendungen basieren auf einer Klasse, die aus der Klasse <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> erbt. Wenn Sie das Verhalten Ihres Diensts bestimmen möchten, können Sie Methoden aus dieser Klasse außer Kraft setzen und ihre Funktionen definieren.  
  
 Folgende Klassen sind wesentlich in die Diensterstellung eingebunden:  
  
- <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>: Beim Erstellen eines Diensts setzen Sie Methoden aus der Klasse <xref:System.ServiceProcess.ServiceBase> außer Kraft und definieren den Code, um zu bestimmen, wie Ihr Dienst in dieser geerbten Klasse funktioniert.  
  
- <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> und <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType>: Mithilfe dieser Klassen lässt sich Ihr Dienst installieren und deinstallieren.  
  
 Darüber hinaus kann die Klasse <xref:System.ServiceProcess.ServiceController> für die Bearbeitung des Diensts selbst verwendet werden. Diese Klasse ist nicht in die Erstellung eines Diensts eingebunden, kann jedoch für das Starten und Beenden des Diensts, für die Übergabe von Befehlen und für die Rückgabe einer Reihe von Enumerationen verwendet werden.  
  
## <a name="defining-your-services-behavior"></a>Definieren des Verhaltens Ihres Diensts  
 In Ihrer Dienstklasse setzen Sie die Funktionen der Basisklasse außer Kraft, die bestimmen, was geschieht, wenn der Status Ihres Diensts im Dienststeuerungs-Manager geändert wird. Die Klasse <xref:System.ServiceProcess.ServiceBase> macht folgende Methoden verfügbar, die Sie außer Kraft setzen können, um benutzerdefiniertes Verhalten hinzuzufügen.  
  
|Methode|Grund für die Außerkraftsetzung|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Angabe, welche Maßnahmen ergriffen werden sollten, wenn Ihr Dienst ausgeführt wird. Sie müssen in dieser Prozedur Code schreiben, damit Ihr Dienst sinnvolle Arbeit leistet.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Angabe, was geschehen soll, wenn Ihr Dienst angehalten wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Angabe, was geschehen soll, wenn Ihr Dienst beendet wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Angabe, was geschehen soll, wenn Ihr Dienst wieder aufgenommen wird und normal funktioniert, nachdem er angehalten wurde.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Angabe, was unmittelbar vor dem Herunterfahren Ihres Systems geschehen soll, wenn Ihr Dienst zu diesem Zeitpunkt ausgeführt wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Angabe, was geschehen soll, wenn Ihr Dienst einen benutzerdefinierten Befehl empfängt. Weitere Informationen zu benutzerdefinierten Befehlen finden Sie auf MSDN Online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Angabe, wie der Dienst reagieren soll, wenn ein Energieverwaltungsereignis empfangen wird, wie z.B. ein niedriger Akkustand oder ein ausgesetzter Vorgang.|  
  
> [!NOTE]
> Diese Methoden stellen Status dar, die der Dienst in seiner Lebensdauer durchläuft: Er geht von einem Status in den nächsten über. So wird der Dienst niemals auf den Befehl <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> reagieren, bevor nicht <xref:System.ServiceProcess.ServiceBase.OnStart%2A> aufgerufen wurde.  
  
 Es gibt einige andere Eigenschaften und Methoden, die von Interesse sind. Dazu gehören:  
  
- Die Methode <xref:System.ServiceProcess.ServiceBase.Run%2A> in der Klasse <xref:System.ServiceProcess.ServiceBase>. Dies ist der Haupteinstiegspunkt für den Dienst. Wenn Sie einen Dienst mit der Windows-Dienstvorlage erstellen, wird Code in die Methode `Main` Ihrer Anwendung eingefügt, um den Dienst auszuführen. Dieser Code sieht wie folgt aus:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    > In diesen Beispielen wird ein Array vom Typ <xref:System.ServiceProcess.ServiceBase> verwendet, in das jeder Dienst hinzugefügt werden kann, den Ihre App enthält. Anschließend können sämtliche Dienste zusammen ausgeführt werden. Wenn Sie nur einen Dienst erstellen, empfiehlt es sich jedoch, nicht das Array zu verwenden, sondern einfach ein neues Objekt zu deklarieren, das aus <xref:System.ServiceProcess.ServiceBase> erbt, und dieses Objekt auszuführen. Ein Beispiel finden Sie unter [Gewusst wie: Programmgesteuertes Schreiben von Diensten](how-to-write-services-programmatically.md).  
  
- Eine Reihe von Eigenschaften in der Klasse <xref:System.ServiceProcess.ServiceBase>. Mit diesen Eigenschaften wird bestimmt, welche Methoden in Ihrem Dienst aufgerufen werden können. Wenn die Eigenschaft <xref:System.ServiceProcess.ServiceBase.CanStop%2A> beispielsweise auf `true` festgelegt wird, kann die Methode <xref:System.ServiceProcess.ServiceBase.OnStop%2A> in Ihrem Dienst aufgerufen werden. Wenn die Eigenschaft <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> auf `true` festgelegt wird, können die Methoden <xref:System.ServiceProcess.ServiceBase.OnPause%2A> und <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> aufgerufen werden. Wenn Sie eine dieser Eigenschaften auf `true` festlegen, sollten Sie anschließend die Verarbeitung für die zugeordneten Methoden außer Kraft setzen und definieren.  
  
    > [!NOTE]
    > Ihr Dienst muss mindestens <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> außer Kraft setzen, um hilfreich zu sein.  
  
 Sie können auch die Komponente <xref:System.ServiceProcess.ServiceController> verwenden, um mit dem vorhandenen Dienst zu kommunizieren und sein Verhalten zu steuern.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
- [How to: Erstellen von Windows-Diensten](how-to-create-windows-services.md)
