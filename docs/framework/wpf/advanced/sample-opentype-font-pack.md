---
title: OpenType-Beispielschriftartenpaket
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: 93bba86801ec4971e884cb4703d7a6323a2e94fe
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44273790"
---
# <a name="sample-opentype-font-pack"></a>OpenType-Beispielschriftartenpaket
Dieses Thema enthält eine Übersicht über die [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Beispielschriftarten, die mit [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] verteilt sind. Die Beispielschriftarten unterstützen erweiterte [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Features, die von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen verwendet werden können .  
  
  
<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Schriftarten im OpenType-Schriftartenpaket  
 Das [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] bietet eine Reihe von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Beispielschriftarten, mit denen Sie beim Erstellen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen verwenden können. Die Beispielschriftarten werden unter der Lizenz von Ascender Corporation bereitgestellt. Diese Schriftarten implementieren nur einen Teil der Features, die vom [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Format festgelegt sind. Die folgende Tabelle enthält die Namen der [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Beispielschriftarten.  
  
|**Name**|**Datei**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Fett|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero fett|Pescab.ttf|  
  
 Die folgende Abbildung zeigt, wie die [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Beispielschriftarten aussehen.  
  
 ![Liste der Schriftartennamen im beispielschriftartpaket](../../../../docs/framework/wpf/advanced/media/samplefontpack01.gif "samplefontpack01")  
Schriftarten im OpenType-Schriftartenpaket  
  
 Die Beispielschriftarten werden unter der Lizenz von Ascender Corporation bereitgestellt. Ascender ist ein Anbieter von erweiterten Schriftartprodukten. Auf der [Ascender Corporation Website](https://go.microsoft.com/fwlink/?LinkId=182627) finden Sie erweiterte oder benutzerdefinierte Versionen, um die Beispielschriftarten zu lizenzieren.  
  
> [!NOTE]
>  Aus diesem Grund liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anders verteilen.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Installieren der Schriftarten  
 Sie haben die Möglichkeit zum Installieren der [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Beispielschriftarten auf das [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Standardschriftartenverzeichnis **\WINDOWS\Fonts**. Verwenden Sie die Systemsteuerung „Schriftarten“, um die Schriftarten zu installieren. Sobald sich diese Schriftarten auf Ihrem Computer befinden, können alle Anwendungen darauf zugreifen, die auf die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Standardschriftarten verweisen. Sie können eine repräsentative Anzahl an Zeichen in mehreren Schriftgraden anzeigen, indem Sie doppelt auf die Schriftartendatei klicken. Der folgende Screenshot zeigt die Schriftartendatei Lindsey, Linds.ttf.  
  
 ![Schriftart Lindsey &#40;OpenType&#41;](../../../../docs/framework/wpf/advanced/media/typographyinwpf-04.png "TypographyInWPF_04")  
Anzeigen der Schriftart Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Verwenden der Schriftarten  
 Es gibt zwei Methoden, um die Schriftarten in Ihrer Anwendung verwenden zu können. Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die nicht als Ressourcen in eine Assembly eingebettet werden. Alternativ können Sie Schriftarten als Projektresourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet sind. Weitere Informationen finden Sie unter [Schriftarten mit Anwendungen verpacken](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Documents.Typography>  
 [Features für OpenType-Schriftarten](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [Verpacken von Schriftarten mit Anwendungen](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
