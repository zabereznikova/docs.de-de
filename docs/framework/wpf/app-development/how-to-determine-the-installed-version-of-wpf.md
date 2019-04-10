---
title: 'Vorgehensweise: Bestimmen der installierten Version von WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305675"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Vorgehensweise: Bestimmen der installierten Version von WPF
Die Versionsnummer für die derzeit installierte Version von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] befindet sich in der **Registrierung**.  
  
 Um die Versionsnummer zu finden:  
  
1. Auf der **starten** Menü klicken Sie auf **ausführen**.  
  
2. In **öffnen**, Typ **regedit.exe**.  
  
3. Öffnen Sie den folgenden Schlüssel:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Versionsnummer befindet sich in der **Version** Wert.
