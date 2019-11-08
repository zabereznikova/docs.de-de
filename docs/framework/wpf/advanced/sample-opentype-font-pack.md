---
title: OpenType-Beispielschriftartenpaket
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: a5b49e2a1f7536fb9d8e8f4dbfc53494dcd1f1ac
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740773"
---
# <a name="sample-opentype-font-pack"></a>OpenType-Beispielschriftartenpaket
Dieses Thema enthält eine Übersicht über die OpenType-Beispiel Schriftarten, die mit dem Windows SDK verteilt werden. Die Beispiel Schriftarten unterstützen erweiterte OpenType-Funktionen, die von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen verwendet werden können.  

<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Schriftarten im OpenType-Schriftartenpaket  
 Der Windows SDK bietet eine Reihe von OpenType-Beispiel Schriftarten, die Sie beim Erstellen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen verwenden können. Die Beispielschriftarten werden unter der Lizenz von Ascender Corporation bereitgestellt. Diese Schriftarten implementieren nur eine Teilmenge der gesamten Features, die im OpenType-Format definiert sind. In der folgenden Tabelle sind die Namen der OpenType-Beispiel Schriftarten aufgeführt.  
  
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
  
 In der folgenden Abbildung wird gezeigt, wie die OpenType-Beispiel Schriftarten aussehen.  
  
 ![Liste der Schriftartennamen im Beispiel-Schriftartpaket](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 Die Beispielschriftarten werden unter der Lizenz von Ascender Corporation bereitgestellt. Ascender ist ein Anbieter von erweiterten Schriftartprodukten. Auf der [Ascender Corporation Website](https://go.microsoft.com/fwlink/?LinkId=182627) finden Sie erweiterte oder benutzerdefinierte Versionen, um die Beispielschriftarten zu lizenzieren.  
  
> [!NOTE]
> Aus diesem Grund liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anders verteilen.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Installieren der Schriftarten  
 Sie haben die Möglichkeit, die OpenType-Beispiel Schriftarten im Standardverzeichnis "Windows-Schriftarten" ( **\Windows\Fonts**) zu installieren. Verwenden Sie die Systemsteuerung „Schriftarten“, um die Schriftarten zu installieren. Sobald sich diese Schriftarten auf dem Computer befinden, sind Sie für alle Anwendungen verfügbar, die auf standardmäßige Windows-Schriftarten verweisen. Sie können eine repräsentative Anzahl an Zeichen in mehreren Schriftgraden anzeigen, indem Sie doppelt auf die Schriftartendatei klicken. Der folgende Screenshot zeigt die Schriftartendatei Lindsey, Linds.ttf.  
  
 ![Schriftart Lindsey &#40;OpenType&#41;](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Anzeigen der Schriftart Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Verwenden der Schriftarten  
 Es gibt zwei Methoden, um die Schriftarten in Ihrer Anwendung verwenden zu können. Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die nicht als Ressourcen in eine Assembly eingebettet werden. Alternativ können Sie Schriftarten als Projektresourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet sind. Weitere Informationen finden Sie unter [Schriftarten mit Anwendungen verpacken](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.Typography>
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [Verpacken von Schriftarten mit Anwendungen](packaging-fonts-with-applications.md)
