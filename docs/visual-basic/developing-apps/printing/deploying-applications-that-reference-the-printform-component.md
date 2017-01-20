---
title: "Deploying Applications That Reference the PrintForm Component (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "PrintForm component [Visual Basic], deploying"
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Deploying Applications That Reference the PrintForm Component (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie eine Anwendung bereitstellen möchten, die auf die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente verweist, muss die Komponente auf dem Zielcomputer installiert sein.  
  
 Die PowerPack\-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169) herunterladen.  
  
## Installieren von PrintForm als erforderliche Komponente  
 Um eine Anwendung erfolgreich bereitzustellen, müssen auch alle Komponenten bereitgestellt werden, auf die die Anwendung verweist. Der Vorgang des Installierens von erforderlichen Komponenten wird als *Bootstrapping* bezeichnet.  
  
 Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente auf Ihrem Entwicklungscomputer installiert ist, wird dem [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]\-Bootstrapperverzeichnis ein Microsoft Visual Basic Power Packs\-Bootstrapperpaket hinzugefügt. Dieses Paket steht dann beim Befolgen der Anweisungen zum Hinzufügen von erforderlichen Komponenten für die Bereitstellung mithilfe von [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] oder eines Windows\-Installationsprogramms zur Verfügung.  
  
 Standardmäßig werden Bootstrappingkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt. Alternativ können Sie die Komponenten über eine URL oder einen Dateifreigabe\-Speicherort bereitstellen und Benutzern so den Download bei Bedarf ermöglichen.  
  
> [!NOTE]
>  Zum Installieren von Bootstrapperkomponenten benötigt der Benutzer möglicherweise Administrator\- oder ähnliche Benutzerberechtigungen auf dem Computer. Im Fall von [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)]\-Anwendungen bedeutet dies, dass die Benutzer Administratorberechtigungen zum Installieren der Anwendung benötigen, unabhängig von der Sicherheitsstufe, die von der Anwendung vorgegeben ist. Nach der Installation können die Benutzer die Anwendung ohne Administratorberechtigungen ausführen.  
  
 Während der Installation werden die Benutzer zur Installation der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente aufgefordert, wenn sie auf dem Zielcomputer nicht vorhanden ist.  
  
 Als Alternative zum Bootstrapping bietet sich eine Vorabbereitstellung der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente mithilfe eines elektronischen Softwareverteilungssystems wie Microsoft Systems Management Server an.  
  
## Siehe auch  
 [How to: Install Prerequisites with a ClickOnce Application](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [Nicht im Build: Auswählen einer Bereitstellungsstrategie](http://msdn.microsoft.com/de-de/ecd632d8-063c-4028-b785-81bba045107b)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)