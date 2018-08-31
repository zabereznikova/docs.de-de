---
title: My.Resources-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 41b6eaa39abfab6cda943162c5c10d1cbeaa9e49
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258029"
---
# <a name="myresources-object"></a>My.Resources-Objekt
Stellt Eigenschaften und Klassen für den Zugriff auf die Ressourcen der Anwendung bereit.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Resources` Objekt bietet Zugriff auf die Ressourcen der Anwendung und das dynamische Abrufen von Ressourcen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 Die `My.Resources` -Objekt macht nur globale Ressourcen verfügbar. Er bietet Zugriff auf die Ressourcendateien, die Formularen zugeordnet. Sie müssen die Formularressourcen aus dem Formular zugreifen.  
  
 Es stehen der Anwendung kulturspezifische Ressourcendateien aus den `My.Resources` Objekt. In der Standardeinstellung die `My.Resources` -Objekt sucht nach Ressourcen aus der Ressourcendatei, die die Kultur in entspricht der <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> Eigenschaft. Allerdings können Sie dieses Verhalten überschreiben, und geben eine bestimmte Kultur, die für die Ressourcen verwendet. Weitere Informationen finden Sie unter [Ressourcen in Desktop-Apps](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften der `My.Resources` Objekt bereitstellen, nur-Lese Zugriff auf die Ressourcen der Anwendung. Verwenden Sie zum Hinzufügen oder Entfernen von Ressourcen, die **Projekt-Designer**. Sie Zugriff auf Ressourcen, die hinzugefügt werden, über die **Projekt-Designer** mit `My.Resources.``resourceName`.  
  
 Sie können auch hinzufügen oder entfernen Sie hierzu Ihr Projekt in Ressourcendateien **Projektmappen-Explorer** und auf **neues Element hinzufügen** oder **vorhandenes Element hinzufügen** aus der  **Projekt** Menü. Sie erreichen auf diese Weise mit hinzugefügten Ressourcen `My.Resources.``resourceFileName`.`resourceName`.  
  
 Jede Ressource verfügt über ein Name, Kategorie und Wert und die ressourceneinstellungen für diese zu ermitteln, wie die Eigenschaft, die Zugriff auf die Ressource in angezeigt wird der `My.Resources` Objekt. Für Ressourcen, die hinzugefügt werden, der **Projekt-Designer**:  
  
-   Den Namen des bestimmt des Namens der Eigenschaft,  
  
-   Die Ressourcendaten ist der Wert der Eigenschaft,  
  
-   Die Kategorie bestimmt den Typ der Eigenschaft:  
  
|Kategorie|Eigenschaftsdatentyp|  
|---|---|  
|**Zeichenfolgen**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Bilder**|<xref:System.Drawing.Bitmap>|  
|**Symbole**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Die <xref:System.IO.UnmanagedMemoryStream> Klasse leitet sich von der <xref:System.IO.Stream> Klasse, damit sie mit Methoden verwendet werden kann, die Streams, wie z. B. verwenden die <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> Methode.|  
|**Dateien**|-   [Zeichenfolge](../../../visual-basic/language-reference/data-types/string-data-type.md) für Textdateien.<br />-   <xref:System.Drawing.Bitmap> für Bilddateien.<br />-   <xref:System.Drawing.Icon> für Symboldateien.<br />-   <xref:System.IO.UnmanagedMemoryStream> für Audiodateien.|  
|**Andere**|Bestimmt, indem die Informationen in des Designers **Typ** Spalte.|  
  
## <a name="classes"></a>Klassen  
 Die `My.Resources` Objekt macht jede Ressourcendatei als eine Klasse mit den Eigenschaften der freigegebenen verfügbar. Der Klassenname ist identisch mit den Namen der Ressourcendatei. Wie im vorherigen Abschnitt beschrieben wird, werden die Ressourcen in einer Ressourcendatei als Eigenschaften in der Klasse verfügbar gemacht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird den Titel eines Formulars auf die Zeichenfolgenressource mit dem Namen `Form1Title` in der Ressourcendatei der Anwendung. Für das Beispiel funktioniert die Anwendung muss eine Zeichenfolge, die mit dem Namen haben `Form1Title` in der Ressourcendatei.  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Symbol des Formulars, auf das Symbol mit dem Namen `Form1Icon` im Ressourcen-Datei der Anwendung gespeichert wird. Für dieses Beispiel funktioniert, müssen die Anwendung ein Symbol mit dem Namen `Form1Icon` in der Ressourcendatei.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Hintergrundbild eines Formulars für die imageressource, die mit dem Namen `Form1Background`, dies ist in der Ressourcendatei der Anwendung. Für dieses Beispiel funktioniert, müssen die Anwendung eine Bildressource, die mit dem Namen `Form1Background` in der Ressourcendatei.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel gibt den Sound, die als audio-Ressource mit dem Namen gespeichert sind `Form1Greeting` in Ressourcendatei der Anwendung. Für dieses Beispiel funktioniert, müssen die Anwendung eine audio-Ressource mit dem Namen `Form1Greeting` in der Ressourcendatei. Die `My.Computer.Audio.Play` Methode ist nur für Windows Forms-Anwendungen verfügbar.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ruft die Kultur Französisch-Version der Ressource, eine Zeichenfolge der Anwendung ab. Die Ressource wird mit dem Namen `Message`. So ändern Sie die Kultur, die die `My.Resources` Objekt verwendet wird, im Beispiel wird <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Für dieses Beispiel funktioniert, die Anwendung muss eine Zeichenfolge, die mit dem Namen haben `Message` in seine Ressource einer Datei, und die Anwendung sollte die Kultur Französisch-Version der Ressourcendatei, Resources.fr-FR.resx verfügen. Wenn die Anwendung keinen die Kultur Französisch-Version der Ressourcendatei, die `My.Resource` Objekt ruft die Ressource ab, aus der Ressourcendatei für die Standardkultur.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Anwendungsressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [Ressourcen in Desktop-Apps](../../../framework/resources/index.md)  

