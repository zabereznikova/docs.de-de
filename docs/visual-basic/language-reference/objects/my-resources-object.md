---
title: My.Resources-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 3d12524706f680434d5b6d8da39c89042bea3281
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867331"
---
# <a name="myresources-object"></a>My.Resources-Objekt

Stellt Eigenschaften und Klassen für den Zugriff auf die Ressourcen der Anwendung bereit.  
  
## <a name="remarks"></a>Bemerkungen  

 Das `My.Resources` -Objekt bietet Zugriff auf die Ressourcen der Anwendung und ermöglicht das dynamische Abrufen von Ressourcen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Anwendungs Ressourcen (.net)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 Das `My.Resources`-Objekt macht nur globale Ressourcen verfügbar. Es bietet keinen Zugriff auf Ressourcendateien, die Formularen zugeordnet sind. Zugriff auf die Formularressourcen erhalten Sie über das Formular.  
  
 Sie können auf die kulturspezifischen Ressourcen Dateien der Anwendung aus dem- `My.Resources` Objekt zugreifen. Standardmäßig sucht das- `My.Resources` Objektressourcen aus der Ressourcen Datei, die mit der Kultur in der-Eigenschaft übereinstimmt <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> . Sie können dieses Verhalten jedoch außer Kraft setzen und eine bestimmte Kultur angeben, die für die Ressourcen verwendet werden soll. Weitere Informationen finden Sie unter [Ressourcen in Desktop-Apps](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Eigenschaften  

 Die Eigenschaften des `My.Resources` -Objekts ermöglichen schreibgeschützten Zugriff auf die Ressourcen Ihrer Anwendung. Verwenden Sie den **Projekt-Designer**, um Ressourcen hinzuzufügen oder zu entfernen. Mithilfe von **Project Designer** `My.Resources.` *resourceName*können Sie auf Ressourcen zugreifen, die über den Projekt-Designer hinzugefügt wurden.  
  
 Sie können Ressourcen Dateien auch hinzufügen oder entfernen, indem Sie das Projekt in **Projektmappen-Explorer** auswählen und dann im Menü **Projekt** auf **Neues Element hinzufügen** oder **Vorhandenes Element hinzufügen** klicken. Mithilfe von `My.Resources.` *resourceFileName* `.` *resourceName*können Sie auf die auf diese Weise hinzugefügten Ressourcen zugreifen.  
  
 Jede Ressource verfügt über einen Namen, eine Kategorie und einen Wert, und mit diesen Ressourcen Einstellungen wird festgelegt, wie die Eigenschaft für den Zugriff auf die Ressource im-Objekt angezeigt wird `My.Resources` . Für Ressourcen, die im **Projekt-Designer**hinzugefügt werden:  
  
- Der Name bestimmt den Namen der Eigenschaft.  
  
- Bei den Ressourcen Daten handelt es sich um den Wert der-Eigenschaft.  
  
- Die Kategorie bestimmt den Typ der Eigenschaft:  
  
|Category|Datentyp der Eigenschaft|  
|---|---|  
|**Zeichenfolgen**|[String](../data-types/string-data-type.md)|  
|**Images**|<xref:System.Drawing.Bitmap>|  
|**Symbole**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Die- <xref:System.IO.UnmanagedMemoryStream> Klasse wird von der- <xref:System.IO.Stream> Klasse abgeleitet, sodass Sie mit Methoden verwendet werden kann, die Streams verwenden, wie z. b. die- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> Methode.|  
|**Dateien**|-   [Zeichenfolge](../data-types/string-data-type.md) für Textdateien.<br />-   <xref:System.Drawing.Bitmap> für Bilddateien.<br />-   <xref:System.Drawing.Icon> für Symbol Dateien.<br />-   <xref:System.IO.UnmanagedMemoryStream> für Sounddateien.|  
|**Andere**|Wird durch die Informationen in der **Type** -Spalte des Designers bestimmt.|  
  
## <a name="classes"></a>Klassen  

 Das- `My.Resources` Objekt macht jede Ressourcen Datei als Klasse mit freigegebenen Eigenschaften verfügbar. Der Klassenname ist identisch mit dem Namen der Ressourcen Datei. Wie im vorherigen Abschnitt beschrieben, werden die Ressourcen in einer Ressourcen Datei als Eigenschaften in der-Klasse verfügbar gemacht.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird der Titel eines Formulars auf die Zeichen folgen Ressource mit dem Namen `Form1Title` in der Anwendungs Ressourcen Datei festgelegt. Damit das Beispiel funktioniert, muss die Anwendung über eine Zeichenfolge mit dem Namen `Form1Title` in der Ressourcen Datei verfügen.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das Symbol des Formulars auf das Symbol festgelegt `Form1Icon` , das in der Ressourcen Datei der Anwendung gespeichert ist. Damit das Beispiel funktioniert, muss die Anwendung über ein Symbol mit dem Namen `Form1Icon` in der Ressourcen Datei verfügen.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das Hintergrundbild eines Formulars auf die Image-Ressource mit dem Namen festgelegt `Form1Background` , die sich in der Anwendungs Ressourcen Datei befindet. Damit dieses Beispiel funktioniert, muss für die Anwendung eine Image-Ressource mit dem Namen in der zugehörigen `Form1Background` Ressourcen Datei vorhanden sein.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird der Sound abgespielt, der als Audioressource `Form1Greeting` mit dem Namen in der Ressourcen Datei der Anwendung gespeichert wird. Damit das Beispiel funktioniert, muss die Anwendung über eine Audioressource mit dem Namen `Form1Greeting` in der Ressourcen Datei verfügen. Die- `My.Computer.Audio.Play` Methode ist nur für Windows Forms Anwendungen verfügbar.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird die französische Kultur Version einer Zeichen folgen Ressource der Anwendung abgerufen. Die Ressource hat den Namen `Message` . Um die Kultur zu ändern, die vom- `My.Resources` Objekt verwendet wird, wird im Beispiel verwendet <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> .  
  
 Damit dieses Beispiel funktioniert, muss die Anwendung über eine Zeichenfolge mit dem Namen `Message` in der Ressourcen Datei verfügen, und die Anwendung sollte die französische Kultur Version der Ressourcen Datei Resources.fr-fr. resx aufweisen. Wenn die Anwendung nicht über die französische Kultur Version der Ressourcen Datei verfügt, ruft das- `My.Resource` Objekt die Ressource aus der Standard-Culture-Ressourcen Datei ab.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwalten von Anwendungsressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Ressourcen in Desktop-Apps](../../../framework/resources/index.md)
