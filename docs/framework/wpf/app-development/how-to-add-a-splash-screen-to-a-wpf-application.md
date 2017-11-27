---
title: "Gewusst wie: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 973f35f6bfa259490a9423bf0b69d676ad968372
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Gewusst wie: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung
In diesem Thema wird gezeigt, wie ein Startfenster hinzufügen oder *Begrüßungsbildschirm*, um eine Windows Presentation Foundation (WPF)-Anwendung.  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a>So fügen Sie einem vorhandenen Image als Begrüßungsbildschirm hinzu  
  
1.  Erstellen Sie oder suchen Sie ein Bild, das Sie für den Begrüßungsbildschirm verwenden möchten. Sie können jedes Bildformat verwenden, die von der Windows Imaging-Komponente (WIC) unterstützt wird. Sie können z. B. BMP, GIF, JPEG, PNG und TIFF-Format verwenden.  
  
2.  Fügen Sie die Abbilddatei der WPF-Anwendungsprojekt. Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
3.  Wählen Sie im Projektmappen-Explorer das Abbild aus.  
  
4.  Klicken Sie im Fenster Eigenschaften auf den Dropdownpfeil für die **Buildvorgang** Eigenschaft.  
  
5.  Wählen Sie **SplashScreen** aus der Dropdown-Liste.  
  
    > [!NOTE]
    >  Wenn Sie nicht sehen die **SplashScreen** aktivieren, sollten Sie unbedingt die Verwendung von [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 oder höher.  
  
6.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Splash-Bildschirm wird in der Mitte des Bildschirms, und klicken Sie dann ausgeblendet wird, wenn das Hauptanwendungsfenster angezeigt wird.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>So entfernen Sie den Begrüßungsbildschirm aus einer Anwendung  
  
1.  Wählen Sie im Projektmappen-Explorer die des Begrüßungsbildschirms.  
  
2.  Legen Sie im Fenster Eigenschaften die **Buildvorgang** auf **keine**.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>So entfernen Sie den Begrüßungsbildschirm aus einer Anwendung  
  
-   Löschen Sie im Projektmappen-Explorer die des Begrüßungsbildschirms.  
  
-   Schließen Sie das Bild des Begrüßungsbildschirms aus dem Projekt ein.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.SplashScreen>  
 [NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
