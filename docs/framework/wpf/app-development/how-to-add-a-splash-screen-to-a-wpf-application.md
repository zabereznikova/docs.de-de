---
title: "Gewusst wie: Hinzuf&#252;gen eines Begr&#252;&#223;ungsbildschirms zu einer WPF-Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Begrüßungsbildschirm [WPF]"
  - "SplashScreen-Klasse [WPF]"
  - "Startfenster [WPF]"
  - "WPF, Begrüßungsbildschirm"
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Hinzuf&#252;gen eines Begr&#252;&#223;ungsbildschirms zu einer WPF-Anwendung
In diesem Thema wird erläutert, wie ein Startfenster oder *Begrüßungsbildschirm* einer WPF\-Anwendung \(Windows Presentation Foundation\) hinzugefügt wird.  
  
### So fügen Sie ein vorhandenes Bild als Begrüßungsbildschirm hinzu  
  
1.  Erstellen oder suchen Sie ein Bild, das Sie für den Begrüßungsbildschirm verwenden möchten.  Sie können jedes Bildformat verwenden, das von der Windows Imaging\-Komponente \(WIC\) unterstützt wird.  Zum Beispiel können Sie BMP, GIF, JPEG, PNG oder TIFF als Format verwenden.  
  
2.  Fügen Sie die Bilddatei dem WPF\-Anwendungsprojekt hinzu.  Weitere Informationen hierzu finden Sie unter [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/de-de/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
3.  Wählen Sie das Bild im Projektmappen\-Explorer aus.  
  
4.  Klicken Sie im Eigenschaftenfenster auf den Dropdownpfeil für die Eigenschaft **Buildvorgang**.  
  
5.  Wählen Sie im Dropdown\-Listenfeld **SplashScreen** aus.  
  
    > [!NOTE]
    >  Wenn Sie die Option **SplashScreen** nicht sehen, stellen Sie sicher, dass Sie [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 oder höher verwenden.  
  
6.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Das Bild des Begrüßungsbildschirms wird in der Mitte des Bildschirms angezeigt und wird ausgeblendet, wenn das Fenster der Hauptanwendung eingeblendet wird.  
  
### So entfernen Sie den Begrüßungsbildschirm aus einer Anwendung  
  
1.  Wählen Sie im Projektmappen\-Explorer das Bild des Begrüßungsbildschirms aus.  
  
2.  Legen Sie im Eigenschaftenfenster **Buildvorgang** auf **Keiner** fest.  
  
### So entfernen Sie den Begrüßungsbildschirm aus einer Anwendung  
  
-   Löschen Sie im Projektmappen\-Explorer das Bild des Begrüßungsbildschirms.  
  
-   Schließen Sie das Bild des Begrüßungsbildschirms vom Projekt aus.  
  
## Siehe auch  
 <xref:System.Windows.SplashScreen>   
 [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/de-de/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)