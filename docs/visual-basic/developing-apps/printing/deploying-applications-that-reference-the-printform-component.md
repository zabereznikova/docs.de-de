---
title: Bereitstellen von Anwendungen, die auf die PrintForm-Komponente (Visual Basic) verweisen.
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
ms.openlocfilehash: 3dd7c348c4dc36a7ff64e76a93c05ddb24837079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584695"
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Bereitstellen von Anwendungen, die auf die PrintForm-Komponente (Visual Basic) verweisen.
Wenn Sie eine Anwendung bereitstellen möchten, die auf die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente verweist, muss die Komponente auf dem Zielcomputer installiert sein.  
  
 Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Installieren von PrintForm als erforderliche Komponente  
 Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist. Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.  
  
 Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Komponente auf dem Entwicklungscomputer installiert ist, wird das Visual Studio-Bootstrapper-Verzeichnis ein Microsoft Visual Basic Power Packs-Bootstrapperpaket hinzugefügt. Dieses Paket steht dann beim Befolgen der Anweisungen zum Hinzufügen von erforderlichen Komponenten für die Bereitstellung mithilfe von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] oder eines Windows-Installationsprogramms zur Verfügung.  
  
 Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt. Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.  
  
> [!NOTE]
>  Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer. Im Fall von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] -Anwendungen bedeutet dies, dass die Benutzer Administratorberechtigungen zum Installieren der Anwendung benötigen, unabhängig von der Sicherheitsstufe, die von der Anwendung vorgegeben ist. Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.  
  
 Während der Installation werden die Benutzer zur Installation der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente aufgefordert, wenn sie auf dem Zielcomputer nicht vorhanden ist.  
  
 Als Alternative zum Bootstrapping bietet sich eine Vorabbereitstellung der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente mithilfe eines elektronischen Softwareverteilungssystems wie Microsoft Systems Management Server an.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [PrintForm-Komponente](../../../visual-basic/developing-apps/printing/printform-component.md)
