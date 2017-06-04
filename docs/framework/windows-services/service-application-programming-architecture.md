---
title: "Service Application Programming Architecture | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ServiceController components, programming architecture"
  - "ServiceBase class, service states"
  - "Windows Service applications, code model"
  - "services, programming architecture"
  - "ServiceController class"
  - "services, states"
  - "ServiceProcessInstaller class, service application code model"
  - "Windows Service applications, states"
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# Service Application Programming Architecture
Windows\-Dienstanwendungen basieren auf einer Klasse, die von der <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName>\-Klasse erbt.  Das Verhalten eines Diensts wird bestimmt, indem Methoden aus dieser Klasse überschrieben und Funktionen für sie definiert werden.  
  
 Nachfolgend werden die Hauptklassen aufgelistet, mit denen Dienste erstellt werden:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName>: Wenn ein Dienst erstellt wird, werden Methoden aus der <xref:System.ServiceProcess.ServiceBase>\-Klasse überschrieben und Code definiert, um die Funktionsweise des Diensts in dieser geerbten Klasse zu bestimmen.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=fullName> und <xref:System.ServiceProcess.ServiceInstaller?displayProperty=fullName>: Verwenden Sie diese Klassen, um den Dienst zu installieren und zu deinstallieren.  
  
 Zusätzlich kann mithilfe der Klasse <xref:System.ServiceProcess.ServiceController> der Dienst selbst geändert werden.  Diese Klasse spielt beim Erstellen von Diensten keine Rolle. Mit ihr können jedoch Dienste gestartet, beendet und Befehle an sie übergeben werden. Außerdem ist es möglich, eine Reihe von Aufzählungen zurückzugeben.  
  
## Festlegen des Verhaltens eines Diensts  
 In der Dienstklasse werden Funktionen der Basisklasse überschrieben, die festlegen, was geschieht, wenn der Status des Diensts im Dienststeuerungs\-Manager geändert wird.  Von der <xref:System.ServiceProcess.ServiceBase>\-Klasse werden die folgenden Methoden verfügbar gemacht. Benutzerdefiniertes Verhalten kann hinzugefügt werden, indem sie überschrieben werden.  
  
|Methode|Zweck des Überschreibens|  
|-------------|------------------------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Angeben, welche Aktionen vorgenommen werden, wenn der Diensts gestartet wird.  Es muss Code in diese Prozedur geschrieben werden, damit ein Dienst nützliche Arbeiten durchführen kann.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Angeben, was geschehen soll, wenn der Dienst angehalten wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Angeben, was geschehen soll, wenn der Dienst beendet wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Angeben, was geschehen soll, wenn vom Dienst nach dem Anhalten die normale Funktion fortgesetzt wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Angeben, was geschehen soll, wenn das Herunterfahren des Systems unmittelbar bevorsteht, sofern der Dienst zu diesem Zeitpunkt ausgeführt wird.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Angeben, was geschehen soll, wenn vom Dienst ein benutzerdefinierter Befehl empfangen wird.  Weitere Informationen über benutzerdefinierte Befehle finden Sie in MSDN Online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Angeben, wie von dem Dienst beim Empfangen eines Energieverwaltungsereignisses reagiert wird, z. B. niedriger Akkustand oder Standbymodus.|  
  
> [!NOTE]
>  Diese Methoden stellen die Zustandswerte dar, die ein Dienst während seiner Lebensdauer durchläuft. Der Übergang des Diensts erfolgt von einem Zustand zum nächsten.  Der Dienst reagiert beispielsweise erst auf einen <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>\-Befehl, wenn zuvor <xref:System.ServiceProcess.ServiceBase.OnStart%2A> aufgerufen wurde.  
  
 Verschiedene weitere Eigenschaften und Methoden sind von Interesse.  Dazu gehören:  
  
-   Die <xref:System.ServiceProcess.ServiceBase.Run%2A>\-Methode für die <xref:System.ServiceProcess.ServiceBase>\-Klasse.  Sie stellt den Haupteinspringpunkt für einen Dienst dar.  Wenn ein Dienst mit der Vorlage für Windows\-Dienste erstellt wird, wird Code in die `Main`\-Methode der Anwendung eingefügt, damit der Dienst ausgeführt wird.  Der Code sieht folgendermaßen aus:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  In diesen Beispielen wird ein Array vom Typ <xref:System.ServiceProcess.ServiceBase> verwendet. Zu diesem können alle Dienste hinzugefügt werden, die in der Anwendung enthalten sind. Anschließend können alle Dienste zusammen ausgeführt werden.  Wenn jedoch nur ein einzelner Dienst erstellt wird, besteht keine Notwendigkeit, das Array zu verwenden. In diesem Fall kann einfach ein neues Objekt erstellt und ausgeführt werden, das von <xref:System.ServiceProcess.ServiceBase> erbt.  Ein entsprechendes Beispiel finden Sie unter [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Eine Reihe von Eigenschaften der <xref:System.ServiceProcess.ServiceBase>\-Klasse,  mit denen bestimmt wird, welche Methoden von einem Dienst aufgerufen werden können.  Wenn beispielsweise die <xref:System.ServiceProcess.ServiceBase.CanStop%2A>\-Eigenschaft auf `true` festgelegt ist, kann die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>\-Methode für den Dienst aufgerufen werden.  Wenn die <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>\-Eigenschaft auf `true` festgelegt ist, kann die <xref:System.ServiceProcess.ServiceBase.OnPause%2A>\-Methode und die <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>\-Methode aufgerufen werden.  Wenn eine dieser Eigenschaften auf `true` festgelegt wird, müssen die zugeordneten Methoden überschrieben werden, und es ist notwendig, ihre Verarbeitung zu definieren.  
  
    > [!NOTE]
    >  Der Dienst muss in jedem Fall <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> überschreiben.  
  
 Für die Kommunikation mit einem vorhandenen Dienst und die Steuerung seines Verhaltens kann außerdem eine Komponente mit dem Namen <xref:System.ServiceProcess.ServiceController> verwendet werden.  
  
## Siehe auch  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)