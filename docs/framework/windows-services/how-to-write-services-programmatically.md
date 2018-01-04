---
title: 'Gewusst wie: Programmgesteuertes Schreiben von Diensten'
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
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: cdb9c7bba564b71bfba86076218e48610cf73076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-services-programmatically"></a>Gewusst wie: Programmgesteuertes Schreiben von Diensten
Wenn Sie nicht die Projektvorlage Windows-Dienst verwenden möchten, können Sie durch Einrichten der Vererbung und anderer Infrastrukturelemente eigene Dienste schreiben. Sobald Sie einen Dienst programmgesteuert erstellen, müssen sie mehrere Schritte ausführen, die andernfalls von der Vorlage behandelt würden:  
  
-   Sie müssen die Dienstklasse einrichten, damit sie von der <xref:System.ServiceProcess.ServiceBase>-Klasse erbt.  
  
-   Sie müssen für das Dienstprojekt eine `Main`-Methode erstellen, von der die auszuführenden Dienste festgelegt werden. Des Weiteren muss von ihr die <xref:System.ServiceProcess.ServiceBase.Run%2A>-Methode für die Dienste aufgerufen werden.  
  
-   Sie müssen die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Prozedur und die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Prozedur überschreiben und den Code einfügen, den diese ausführen sollen.  
  
### <a name="to-write-a-service-programmatically"></a>So schreiben Sie einen Dienst programmgesteuert  
  
1.  Erstellen Sie ein leeres Projekt und einen Verweis auf die notwendigen Namespaces, indem Sie die folgenden Schritte ausführen:  
  
    1.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **Verweise** Knoten, und klicken Sie auf **Verweis hinzufügen**.  
  
    2.  Auf der **.NET Framework** Registerkarte, einen Bildlauf zu **"System.dll"** , und klicken Sie auf **wählen**.  
  
    3.  Führen Sie einen Bildlauf zum **System.ServiceProcess.dll** , und klicken Sie auf **wählen**.  
  
    4.  Klicken Sie auf **OK**.  
  
2.  Fügen Sie eine Klasse hinzu, und konfigurieren Sie diese, damit sie von <xref:System.ServiceProcess.ServiceBase> erbt:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Konfigurieren Sie die Dienstklasse, indem Sie folgenden Code hinzufügen:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Erstellen Sie für die Klasse eine `Main`-Methode, und verwenden Sie diese zum Definieren des Diensts, den diese Klasse enthält. `userService1` ist der Name der Klasse:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode, und definieren Sie die Verarbeitung beim Starten des Diensts.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Überschreiben sie alle anderen Methoden, für die Sie benutzerdefinierte Verarbeitung definieren möchten. Schreiben Sie Code, mit dem Sie bestimmen, welche Aktionen vom Dienst in den einzelnen Fällen ausgeführt werden sollen.  
  
7.  Fügen Sie die für die Dienstanwendung erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Erstellen Sie das Projekt, indem Sie auswählen **Projektmappe** aus der **erstellen** Menü.  
  
    > [!NOTE]
    >  Drücken Sie nicht F5, um das Projekt auszuführen. Dienstprojekte können auf diese Weise nicht ausgeführt werden.  
  
9. Erstellen Sie ein Setup-Projekt und die benutzerdefinierten Aktionen, um den Dienst zu installieren. Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Installieren Sie den Dienst. Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Vorgehensweise: Protokollinformationen über Dienste](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
