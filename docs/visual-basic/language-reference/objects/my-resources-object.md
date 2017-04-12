---
title: My.Resources-Objekt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
dev_langs:
- VB
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 6ad5bd4e33438256719b59cb0936cf6bc8525ab1
ms.lasthandoff: 03/13/2017

---
# <a name="myresources-object"></a>My.Resources-Objekt
Stellt Eigenschaften und Klassen für den Zugriff auf die Ressourcen der Anwendung bereit.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Resources` Objekt ermöglicht den Zugriff auf die Ressourcen der Anwendung und das dynamische Abrufen von Ressourcen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Ressourcen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).  
  
 Die `My.Resources` -Objekt macht nur globale Ressourcen verfügbar. Es bietet keine Zugriff auf Ressourcendateien, die Formularen zugeordnet. Sie müssen die Ressourcen des Formulars aus dem Formular zugreifen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Sie können die Anwendung kulturspezifische Ressourcendateien aus zugreifen die `My.Resources` Objekt. In der Standardeinstellung die `My.Resources` -Objekt sucht nach Ressourcen aus der Ressourcendatei, die die Kultur in entspricht der <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>Eigenschaft.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> Allerdings können Sie dieses Verhalten überschreiben und angeben eine bestimmte Kultur für die Ressourcen verwendet. Weitere Informationen finden Sie unter [Ressourcen in Desktop-Apps](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften der `My.Resources` Objekt nur-Lese Zugriff auf die Ressourcen der Anwendung bereitstellen. Verwenden Sie zum Hinzufügen oder Entfernen von Ressourcen, die **Projekt-Designer**. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von Ressourcen](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Sie Zugriff auf Ressourcen hinzugefügt, durch die **Projekt-Designer** mit `My.Resources.``resourceName`.  
  
 Können Sie auch hinzufügen oder Entfernen von Ressourcendateien wählen Sie Ihr Projekt in **Projektmappen-Explorer** und auf **neues Element hinzufügen** oder **vorhandenes Element hinzufügen** aus der **Projekt** Menü. Sie können auf diese Weise mit hinzugefügten Ressourcen zugreifen `My.Resources.``resourceFileName`.`resourceName`.  
  
 Jede Ressource verfügt über einen Namen, die Kategorie und den Wert, und diese ressourceneinstellungen bestimmen, wie in die Eigenschaft Zugriff auf die Ressource angezeigt wird die `My.Resources` Objekt. Für Ressourcen hinzugefügt wurden, die **Projekt-Designer**:  
  
-   Der Name bestimmt den Namen der Eigenschaft,  
  
-   Die Ressourcendaten ist der Wert der Eigenschaft,  
  
-   Die Kategorie bestimmt den Typ der Eigenschaft:  
  
|Kategorie|Datentyp der Eigenschaft|  
|---|---|  
|**Zeichenfolgen**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Bilder**|<xref:System.Drawing.Bitmap></xref:System.Drawing.Bitmap>|  
|**Symbole**|<xref:System.Drawing.Icon></xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream></xref:System.IO.UnmanagedMemoryStream><br /><br /> Die <xref:System.IO.UnmanagedMemoryStream>Klasse leitet sich von der <xref:System.IO.Stream>-Klasse mit Methoden verwendet werden, die Streams, z. B. akzeptieren die <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>-Methode.</xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> </xref:System.IO.Stream> </xref:System.IO.UnmanagedMemoryStream>|  
|**Dateien**|-   [Zeichenfolge](../../../visual-basic/language-reference/data-types/string-data-type.md) für Textdateien.<br />- <xref:System.Drawing.Bitmap>für Bilddateien.</xref:System.Drawing.Bitmap><br />- <xref:System.Drawing.Icon>für Symboldateien.</xref:System.Drawing.Icon><br />- <xref:System.IO.UnmanagedMemoryStream>Audiodateien.</xref:System.IO.UnmanagedMemoryStream>|  
|**Andere**|Anhand der Informationen in den Designer **Typ** Spalte.|  
  
## <a name="classes"></a>Klassen  
 Das `My.Resources` -Objekt macht jede Ressourcendatei als Klasse mit freigegebenen Eigenschaften verfügbar. Der Name der Klasse ist identisch mit den Namen der Ressourcendatei. Wie im vorherigen Abschnitt beschrieben, werden die Ressourcen in einer Ressourcendatei als Eigenschaften in der Klasse verfügbar gemacht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Titel eines Formulars auf die Zeichenfolgenressource mit dem Namen `Form1Title` in der Ressourcendatei für die Anwendung. Für dieses Beispiel funktioniert, müssen die Anwendung eine Zeichenfolge mit dem Namen `Form1Title` in der Ressourcendatei. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von Ressourcen](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!code-vb[VbVbalrMyResources&#1;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Symbol des Formulars auf das Symbol mit dem Namen `Form1Icon` , die in der Ressourcendatei der Anwendung gespeichert ist. Für dieses Beispiel funktioniert, müssen die Anwendung ein Symbol mit dem Namen `Form1Icon` in der Ressourcendatei.  
  
 [!code-vb[VbVbalrMyResources&#2;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Hintergrundbild eines Formulars auf die Bildressource mit der Bezeichnung `Form1Background`, die in der Ressourcendatei für die Anwendung ist. Für dieses Beispiel funktioniert, müssen die Anwendung Bildressource `Form1Background` in der Ressourcendatei.  
  
 [!code-vb[VbVbalrMyResources&3;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel gibt den Sound, die als audio-Ressource mit dem Namen gespeichert wird `Form1Greeting` in der Ressourcendatei der Anwendung. Für dieses Beispiel funktioniert, müssen die Anwendung eine audio-Ressource mit dem Namen `Form1Greeting` in der Ressourcendatei. Die `My.Computer.Audio.Play` Methode ist nur für Windows Forms-Anwendung verfügbar.  
  
 [!code-vb[VbVbalrMyResources&4;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ruft die Kultur Französisch-Version einer Zeichenfolgenressource der Anwendung ab. Die Ressource wird mit dem Namen `Message`. So ändern Sie die Kultur, die die `My.Resources` Objekt verwendet, das Beispiel verwendet <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>  
  
 Für dieses Beispiel funktioniert, müssen die Anwendung eine Zeichenfolge mit dem Namen `Message` in die Ressource einer Datei und der Anwendung sollten die Kultur Französisch-Version der Ressourcendatei "Ressourcen.fr-FR.resx" aufweisen. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von Ressourcen](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Wenn die Anwendung keine der Kultur Französisch-Version der Ressourcendatei, die `My.Resource` Objekt ruft die Ressource aus der Ressourcendatei für die Standardkultur ab.  
  
 [!code-vb[VbVbalrMyResources&#10;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Hinzufügen oder Entfernen von Ressourcen](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [Verwalten von Anwendungsressourcen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)   
 [Ressourcen in Desktop-Apps](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)   
 [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)
