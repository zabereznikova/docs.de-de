---
title: "My.Resources Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.Resources"
  - "My.Resources.MyResources.ResourceManager"
  - "My.Resources.MyResources.Culture"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Resources object"
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# My.Resources Object
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Stellt Eigenschaften und Klassen für den Zugriff auf die Ressourcen der Anwendung bereit.  
  
## Hinweise  
 Das `My.Resources`\-Objekt ermöglicht den Zugriff auf die Ressourcen der Anwendung und das dynamische Abrufen von Ressourcen für die Anwendung.  Weitere Informationen finden Sie unter [Verwalten von Anwendungsressourcen \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
 Das `My.Resources`\-Objekt macht nur globale Ressourcen verfügbar.  Es stellt keinen Zugriff auf Formularen zugeordnete Ressourcendateien bereit.  Sie müssen auf die Formularressourcen vom Formular aus zugreifen.  Weitere Informationen finden Sie unter [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/de-de/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Sie können auf die kulturspezifischen Ressourcendateien der Anwendung über das `My.Resources`\-Objekt zugreifen.  Das `My.Resources`\-Objekt sucht standardmäßig nach Ressourcen aus der Ressourcendatei, die mit der Kultur in der <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>\-Eigenschaft übereinstimmt.  Sie können dieses Verhalten jedoch überschreiben und eine bestimmte Kultur angeben, die für die Ressourcen verwendet werden soll.  Weitere Informationen finden Sie unter [Ressourcen in Desktop\-Apps](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
## Eigenschaften  
 Die Eigenschaften des `My.Resources`\-Objekts stellen schreibgeschützten Zugriff auf die Ressourcen der Anwendung bereit.  Um Ressourcen hinzuzufügen oder zu entfernen, verwenden Sie den **Projekt\-Designer**.  Weitere Informationen finden Sie unter [How to: Add or Remove Resources](http://msdn.microsoft.com/de-de/7b77bc06-3952-4799-b029-def3f8f7f88d).  Der Zugriff auf Ressourcen, die mit dem **Projekt\-Designer** hinzugefügt wurden, erfolgt unter Verwendung von `My.Resources.``resourceName`.  
  
 Sie können Ressourcendateien auch hinzufügen oder entfernen, indem Sie im **Projektmappen\-Explorer** das Projekt auswählen und im Menü **Projekt** auf **Neues Element hinzufügen** oder **Vorhandenes Element hinzufügen** klicken.  Der Zugriff auf Ressourcen, die auf diese Weise hinzugefügt wurden, erfolgt unter Verwendung von `My.Resources.``resourceFileName`.`resourceName`.  
  
 Jede Ressource verfügt über einen Namen, eine Kategorie und einen Wert, und diese Ressourceneinstellungen bestimmen, wie die Eigenschaft für den Zugriff auf die Ressource im `My.Resources`\-Objekt dargestellt wird.  Für im **Projekt\-Designer** hinzugefügte Ressourcen gelten folgende Bedingungen:  
  
-   Der Name bestimmt den Namen der Eigenschaft.  
  
-   Die Ressourcendaten sind der Wert der Eigenschaft.  
  
-   Die Kategorie bestimmt den Typ der Eigenschaft:  
  
|||  
|-|-|  
|Kategorie|Datentyp der Eigenschaft|  
|**Zeichenfolgen**|[Zeichenfolge](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Bilder**|<xref:System.Drawing.Bitmap>|  
|**Symbole**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Die <xref:System.IO.UnmanagedMemoryStream>\-Klasse wird von der <xref:System.IO.Stream>\-Klasse abgeleitet und kann daher für Methoden verwendet werden, die Streams akzeptieren, z. B. für die <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>\-Methode.|  
|**Dateien**|-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) für Textdateien.<br />-   <xref:System.Drawing.Bitmap> für Bilddateien.<br />-   <xref:System.Drawing.Icon> für Symboldateien.<br />-   <xref:System.IO.UnmanagedMemoryStream> für Audiodateien.|  
|**Andere**|Hängt von den Informationen in der Spalte **Typ** des Designers ab.|  
  
## Klassen  
 Das `My.Resources`\-Objekt macht jede Ressourcendatei als Klasse mit freigegebenen Eigenschaften verfügbar.  Der Klassenname stimmt mit dem Namen der Ressourcendatei überein.  Wie im vorherigen Abschnitt beschrieben, werden die Ressourcen in einer Ressourcendatei in der Klasse als Eigenschaften verfügbar gemacht.  
  
## Beispiel  
 In diesem Beispiel wird der Titel eines Formulars zur Zeichenfolgenressource fest, die `Form1Title` in der Anwendungsressourcendatei benannt ist.  Damit das Beispiel für die Anwendung ausgeführt werden kann, muss eine Zeichenfolge in der Ressourcendatei der `Form1Title` .  Weitere Informationen finden Sie unter [How to: Add or Remove Resources](http://msdn.microsoft.com/de-de/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#1)]  
  
## Beispiel  
 In diesem Beispiel wird das Symbol des Formulars auf das Symbol `Form1Icon` festgelegt, das in der Ressourcendatei der Anwendung gespeichert ist.  Damit das Beispiel für die Anwendung muss ein Symbol verfügen, das `Form1Icon` in der Ressourcendatei bezeichnet wird.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#2)]  
  
## Beispiel  
 In diesem Beispiel wird das Hintergrundbild eines Formulars zur Bildressource fest, die `Form1Background`, die in der Anwendungsressourcendatei ist.  Für dieses Beispiel muss die Anwendung eine Bildressource verfügen, die `Form1Background` in der Ressourcendatei bezeichnet wird.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#3)]  
  
## Beispiel  
 Dieses Beispiel gibt den Sound als Audiodaten Ressource gespeichert ist, die `Form1Greeting` in der Ressourcendatei der Anwendung.  Damit das Beispiel für die Anwendung muss eine Audio\- Ressource verfügen, die `Form1Greeting` in der Ressourcendatei bezeichnet wird.  Die `My.Computer.Audio.Play`\-Methode ist nur für Windows Forms\-Anwendungen verfügbar.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#4)]  
  
## Beispiel  
 In diesem Beispiel wird die Französisch\-Kultur Version einer Zeichenfolgenressource der Anwendung ab.  Die Ressource wird `Message`benannt.  Um die Kultur zu ändern, die das `My.Resources`\-Objekt verwendet, wird im Beispiel <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Für dieses Beispiel muss die Anwendung über eine Zeichenfolge `Message` , die in der Ressourcendatei erstellt, und die Anwendung sollte die Französisch\-Kultur Version der Ressourcendatei, Resources.fr\-FR.resx haben.  Weitere Informationen finden Sie unter [How to: Add or Remove Resources](http://msdn.microsoft.com/de-de/7b77bc06-3952-4799-b029-def3f8f7f88d).  Wenn die Anwendung keine Französisch\-Kultur Version der Ressourcendatei verfügt, ruft das `My.Resource`\-Objekt die Ressource aus der Ressourcendatei ab. Kultur DEFAULT  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#10)]  
  
## Siehe auch  
 [How to: Add or Remove Resources](http://msdn.microsoft.com/de-de/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [Verwalten von Anwendungsressourcen \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet)   
 [Ressourcen in Desktop\-Apps](../Topic/Resources%20in%20Desktop%20Apps.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/de-de/9a96220d-a19b-4de0-9f48-01e5d82679e5)