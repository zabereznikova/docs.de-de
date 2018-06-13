---
title: Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen.
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: bd235bc0b4a7f9978333931ae1dce012c0950374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587504"
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen.
Wenn Sie möchten eine Anwendung bereitstellen, die auf Power Packs-Steuerelemente verweist (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), die Steuerelemente auf dem Zielcomputer installiert werden müssen.  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Installieren die Power Packs-Steuerelemente als erforderliche Komponente  
 Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist. Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.  
  
 Wenn Visual Studio auf Ihrem Computer installiert ist, wird das Visual Studio-Bootstrapper-Verzeichnis ein Power Packs-Bootstrapperpaket hinzugefügt. Dieses Paket steht dann beim Befolgen der Anweisungen zum Hinzufügen von erforderlichen Komponenten für die Bereitstellung mithilfe von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] oder eines Windows-Installationsprogramms zur Verfügung.  
  
 Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt. Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.  
  
> [!NOTE]
>  Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer. Im Fall von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] -Anwendungen bedeutet dies, dass die Benutzer Administratorberechtigungen zum Installieren der Anwendung benötigen, unabhängig von der Sicherheitsstufe, die von der Anwendung vorgegeben ist. Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.  
  
 Während der Installation werden Benutzer aufgefordert, Power Packs-Steuerelemente zu installieren, wenn sie nicht auf dem Zielcomputer vorhanden sind.  
  
 Als Alternative zum bootstrapping können Sie die Power Packs-Steuerelemente vorab bereitstellen, mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [Visual Basic Power Packs-Steuerelemente](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
