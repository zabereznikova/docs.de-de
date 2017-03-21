---
title: Bereitstellen von Anwendungen, die sich auf die PrintForm-Komponente (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 016643329d2ee66ca5a32f155cf91e0ee137f38f
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Bereitstellen von Anwendungen, die sich auf die PrintForm-Komponente (Visual Basic)
Wenn Sie möchten eine Anwendung bereitstellen, verweist die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente, die die Komponente muss auf dem Zielcomputer installiert werden.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Installieren der PrintForm als erforderliche Komponente  
 Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist. Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping*bezeichnet.  
  
 Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente auf dem Entwicklungscomputer installiert ist, ein Microsoft Visual Basic Power Packs-Bootstrapperpaket hinzugefügt wird die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Bootstrapperverzeichnis.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Dieses Paket ist dann verfügbar, wenn das Verfahren zum Hinzufügen von erforderlichen Komponenten für eine [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] oder Windows Installer-Bereitstellung.  
  
 Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt. Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.  
  
> [!NOTE]
>  Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator- oder ähnliche Benutzerberechtigungen auf dem Computer. Für [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] Applications, bedeutet dies, dass der Benutzer Administratorrechte zur Installation der Anwendung, unabhängig von der Sicherheitsstufe, die von der Anwendung angegeben wird. Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.  
  
 Während der Installation werden Benutzer aufgefordert werden, installieren die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente, wenn es nicht auf dem Zielcomputer vorhanden ist.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Als Alternative zum bootstrapping können Sie vorab Bereitstellen der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [PrintForm-Komponente](../../../visual-basic/developing-apps/printing/printform-component.md)
