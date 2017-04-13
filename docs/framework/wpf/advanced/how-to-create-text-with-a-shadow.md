---
title: "Gewusst wie: Erstellen von Text mit einem Schatten | Microsoft Docs"
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
  - "Schatteneffekte in Text"
  - "Text, Schattiert"
  - "Typografie, Schatteneffekte"
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Erstellen von Text mit einem Schatten
Die Beispiele in diesem Abschnitt zeigen, wie Sie einen Schatteneffekt für angezeigten Text erstellen.  
  
## Beispiel  
 Das <xref:System.Windows.Media.Effects.DropShadowEffect>\-Objekt ermöglicht es Ihnen, eine Vielzahl von Schlagschatteneffekten für Objekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu erstellen.  Das folgende Beispiel zeigt einen Text, auf den ein Schlagschatteneffekt angewendet wurde.  In diesem Fall handelt es sich bei dem Schatten um einen weichgezeichneten Schatten, was eine Weichzeichnung der Schattenfarbe bedeutet.  
  
 ![Textschatten mit Weichheit &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
Beispiel für Text mit einem weichgezeichneten Schatten  
  
 Sie können die Breite eines Schattens steuern, indem Sie die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>\-Eigenschaft festlegen.  Ein Wert von `4.0` gibt eine Schattenbreite von 4 Pixel an.  Indem Sie die <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>\-Eigenschaft ändern, können Sie die Intensität des weichgezeichneten Schattens ändern.  Mit dem Wert `0.0` wird angegeben, dass keine Weichzeichnung festgelegt ist.  Im folgenden Codebeispiel wird das Erstellen eines weichgezeichneten Schattens veranschaulicht.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Diese Schatteneffekte durchlaufen nicht die Textrenderingpipeline von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Aus diesem Grund wird ClearType bei der Verwendung dieser Effekte deaktiviert.  
  
 Im folgenden Beispiel wird ein Text angezeigt, auf den ein Schlagschatteneffekt mit scharfer Kontur angewendet wurde.  In diesem Fall wird der Schatten nicht weichgezeichnet.  
  
 ![Textschatten mit Weichheit &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.png "ShadowText02")  
Beispiel für Schlagschatten mit scharfer Kontur  
  
 Sie können einen Schlagschatten mit scharfer Kontur erstellen, indem Sie die <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>\-Eigenschaft auf `0.0` festlegen. Diese Einstellung gibt an, dass keine Weichzeichnung verwendet wird.  Wenn Sie die Richtung des Schattens steuern möchten, ändern Sie die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>\-Eigenschaft.  Legen Sie den Richtungswert dieser Eigenschaft auf einen Wert zwischen `0` und `360` Grad fest.  In der folgenden Abbildung sind die Richtungswerte zum Einstellen der <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>\-Eigenschaft dargestellt.  
  
 ![DropShadow&#45;Gradeinstellung für Schatten](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Richtungsdiagramm für DropShadow  
  
 Im folgenden Codebeispiel wird das Erstellen eines Schattens mit scharfer Kontur veranschaulicht.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## Verwenden eines Weichzeichnereffekts  
 Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> wird zum Erstellen eines schattenähnlichen Effekts verwendet, der hinter einem Textobjekt platziert werden kann.  Wenn Sie einen Bitmap\-Weichzeichnereffekt auf einen Text anwenden, wird der Text in alle Richtungen gleichmäßig weichgezeichnet.  
  
 Im folgenden Beispiel wird ein Weichzeichnereffekt auf einen Text angewendet.  
  
 ![Textschatten mit einem BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
Beispiel für Text mit einem Weichzeichnereffekt  
  
 Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## Verwenden von TranslateTransform \(Verschieben einer Transformation\)  
 Ein <xref:System.Windows.Media.TranslateTransform> wird für die Erstellung eines schattenähnlichen Effekts verwendet, der hinter einem Textobjekt platziert werden kann.  
  
 Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.TranslateTransform> verwendet, um Text zu versetzen.  In diesem Beispiel wird ein Schatteneffekt erzielt, indem die Kopie des Textes hinter dem primären Text geringfügig versetzt wird.  
  
 ![Textschatten mit einem TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.png "ShadowText07")  
Beispiel für Text mit einer Transformation für einen Schatteneffekt  
  
 Das folgende Codebeispiel zeigt, wie eine Transformation für einen Schatteneffekt erstellt wird.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]