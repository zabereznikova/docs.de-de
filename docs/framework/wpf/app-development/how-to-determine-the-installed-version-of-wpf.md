---
title: Ermitteln der installierten Version von WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735697"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Gewusst wie: Bestimmen der installierten WPF-Version
Die Versionsnummer für die aktuell installierte Version von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] befindet sich in der **Registrierung**.  
  
 So finden Sie die Versionsnummer:  
  
1. Klicken Sie im **Startmenü** auf **Ausführen**.  
  
2. Geben Sie in **Öffnen**den Befehl **Regedit. exe**ein.  
  
3. Öffnen Sie den folgenden Schlüssel:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Versionsnummer wird im **Versions** Wert gespeichert.
