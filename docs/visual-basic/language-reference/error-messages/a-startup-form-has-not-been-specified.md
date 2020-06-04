---
title: Es wurde kein Startformular angegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 058deb1378ed9218274ae20c8340178f7c8fa58c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409906"
---
# <a name="a-startup-form-has-not-been-specified"></a>Es wurde kein Startformular angegeben.

Die Anwendung verwendet die- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Klasse, gibt jedoch nicht das Start Formular an.  
  
 Dies kann vorkommen, wenn das Kontrollkästchen **Anwendungs Framework aktivieren** im Projekt-Designer aktiviert ist, aber das **Start Formular** nicht angegeben ist. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Geben Sie ein Start Objekt für die Anwendung an.  
  
     Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2. Überschreiben <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Sie die-Methode, um die- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> Eigenschaft auf das Start Formular festzulegen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Übersicht über das Visual Basic-Anwendungsmodell](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
