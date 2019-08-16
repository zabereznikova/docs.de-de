---
title: OpenType-Beispielschriftartenpaket
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: e2b3dc3b95cf81a60494f7a02488067717938e97
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545225"
---
# <a name="sample-opentype-font-pack"></a>OpenType-Beispielschriftartenpaket
Dieses Thema enthält eine Übersicht über die OpenType-Beispiel Schriftarten, die mit [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]dem verteilt werden. Die Beispiel Schriftarten unterstützen erweiterte OpenType-Funktionen, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] von Anwendungen verwendet werden können.  

<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Schriftarten im OpenType-Schriftartenpaket  
 Bietet eine Reihe von OpenType-Beispiel Schriftarten, die Sie beim Erstellen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] von-Anwendungen verwenden können. [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] Die Beispielschriftarten werden unter der Lizenz von Ascender Corporation bereitgestellt. Diese Schriftarten implementieren nur eine Teilmenge der gesamten Features, die im OpenType-Format definiert sind. In der folgenden Tabelle sind die Namen der OpenType-Beispiel Schriftarten aufgeführt.  
  
|**Name**|**File**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Fett|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero fett|Pescab.ttf|  
  
 In der folgenden Abbildung wird gezeigt, wie die OpenType-Beispiel Schriftarten aussehen.  
  
 ![Liste der Schriftartennamen im Beispiel-Schriftartpaket](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 Die Beispielschriftarten werden unter der Lizenz von Ascender Corporation bereitgestellt. Ascender ist ein Anbieter von erweiterten Schriftartprodukten. Auf der [Ascender Corporation Website](https://go.microsoft.com/fwlink/?LinkId=182627) finden Sie erweiterte oder benutzerdefinierte Versionen, um die Beispielschriftarten zu lizenzieren.  
  
> [!NOTE]
>  Aus diesem Grund liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anders verteilen.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Installieren der Schriftarten  
 Sie haben die Möglichkeit, die OpenType-Beispiel Schriftarten in das [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Standardverzeichnis "Fonts" ( **\Windows\Fonts**) zu installieren. Verwenden Sie die Systemsteuerung „Schriftarten“, um die Schriftarten zu installieren. Sobald sich diese Schriftarten auf Ihrem Computer befinden, können alle Anwendungen darauf zugreifen, die auf die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Standardschriftarten verweisen. Sie können eine repräsentative Anzahl an Zeichen in mehreren Schriftgraden anzeigen, indem Sie doppelt auf die Schriftartendatei klicken. Der folgende Screenshot zeigt die Schriftartendatei Lindsey, Linds.ttf.  
  
 ![Lindsey Schriftart &#40;OpenType&#41; ](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Anzeigen der Schriftart Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Verwenden der Schriftarten  
 Es gibt zwei Methoden, um die Schriftarten in Ihrer Anwendung verwenden zu können. Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die nicht als Ressourcen in eine Assembly eingebettet werden. Alternativ können Sie Schriftarten als Projektresourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet sind. Weitere Informationen finden Sie unter [Schriftarten mit Anwendungen verpacken](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.Typography>
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [Verpacken von Schriftarten mit Anwendungen](packaging-fonts-with-applications.md)
