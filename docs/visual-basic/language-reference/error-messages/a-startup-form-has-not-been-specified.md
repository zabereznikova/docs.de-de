---
title: Es wurde kein Startformular angegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 301f249e6222c929d2c513964ecbb21df5fbc47f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976193"
---
# <a name="a-startup-form-has-not-been-specified"></a>Es wurde kein Startformular angegeben.

Die Anwendung verwendet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse, aber nicht das Start Formular.  
  
 Dies kann vorkommen, wenn das Kontrollkästchen **Anwendungs Framework aktivieren** im Projekt-Designer aktiviert ist, aber das **Start Formular** nicht angegeben ist. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Geben Sie ein Start Objekt für die Anwendung an.  
  
     Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2. Überschreiben Sie die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>-Methode, um die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>-Eigenschaft auf das Start Formular festzulegen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
