---
title: Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4d342e655dcfe18ed3b5fc1d2710571ed8e3369e
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Bereitstellen von Anwendungen, die auf Power Packs-Steuerelemente (Visual Studio) verweisen.
Wenn Sie möchten eine Anwendung bereitstellen, die auf Power Packs-Steuerelemente verweist (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), müssen die Steuerelemente auf dem Zielcomputer installiert werden.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Installieren die Power Packs-Steuerelemente als erforderliche Komponente  
 Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist. Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.  
  
 Wenn [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] installiert ist, auf dem Entwicklungscomputer ein Power Packs-Bootstrapperpaket hinzugefügt wird die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Bootstrapperverzeichnis. Dieses Paket ist dann verfügbar, wenn das Verfahren zum Hinzufügen von erforderlichen Komponenten für eine [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] oder Windows Installer-Bereitstellung.  
  
 Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt. Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.  
  
> [!NOTE]
>  Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer. Für [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] Applications, bedeutet dies, dass der Benutzer Administratorrechte zur Installation der Anwendung, unabhängig von der Sicherheitsstufe, die von der Anwendung angegeben wird. Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.  
  
 Während der Installation werden Benutzer aufgefordert, die Power Packs-Steuerelemente zu installieren, wenn sie nicht auf dem Zielcomputer vorhanden sind.  
  
 Als Alternative zum bootstrapping können Sie die Power Packs-Steuerelemente vorab bereitstellen, mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [Visual Basic Power Packs-Steuerelemente](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
