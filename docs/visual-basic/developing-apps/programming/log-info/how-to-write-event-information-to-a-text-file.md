---
title: 'Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: f9abf99a06437f08c65eca69e54760e44a217023
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665755"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="dd919-102">Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd919-102">How to: Write Event Information to a Text File (Visual Basic)</span></span>
<span data-ttu-id="dd919-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="dd919-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="dd919-104">Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry`-Methode zum Protokollieren von Nachverfolgungsinformationen, um eine Datei zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="dd919-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>  
  
### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="dd919-105">Hinzufügen und Konfigurieren des Dateiprotokolllisteners</span><span class="sxs-lookup"><span data-stu-id="dd919-105">To add and configure the file log listener</span></span>  
  
1. <span data-ttu-id="dd919-106">Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="dd919-106">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="dd919-107">\- oder –</span><span class="sxs-lookup"><span data-stu-id="dd919-107">\- or -</span></span>  
  
     <span data-ttu-id="dd919-108">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="dd919-108">If there is no app.config file:</span></span>  
  
    1. <span data-ttu-id="dd919-109">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dd919-109">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2. <span data-ttu-id="dd919-110">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="dd919-110">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3. <span data-ttu-id="dd919-111">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dd919-111">Click **Add**.</span></span>  
  
2. <span data-ttu-id="dd919-112">Suchen Sie den Abschnitt `<listeners>` in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dd919-112">Locate the `<listeners>` section in the application configuration file.</span></span>  
  
     <span data-ttu-id="dd919-113">Sie finden den Abschnitt \<listeners> im Abschnitt \<source> mit dem Namensattribute „DefaultScource“, das sich im Abschnitt \<system.diagnostics> befindet, der wiederum unter dem Abschnitt der höchsten Ebene \<configuration> zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="dd919-113">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>  
  
3. <span data-ttu-id="dd919-114">Fügen Sie dem `<listeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="dd919-114">Add this element to that `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="FileLogListener" />  
    ```  
  
4. <span data-ttu-id="dd919-115">Machen Sie den Abschnitt `<sharedListeners>` im Abschnitt `<system.diagnostics>`, der sich unter dem Abschnitt der höchsten Ebene `<configuration>` befindet.</span><span class="sxs-lookup"><span data-stu-id="dd919-115">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>  
  
5. <span data-ttu-id="dd919-116">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="dd919-116">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="FileLogListener"   
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
              PublicKeyToken=b03f5f7f11d50a3a"  
        initializeData="FileLogListenerWriter"  
        location="Custom"  
        customlocation="c:\temp\" />  
    ```  
  
     <span data-ttu-id="dd919-117">Ändern Sie den Wert des `customlocation`-Attributs in das Protokollverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dd919-117">Change the value of the `customlocation` attribute to the log directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd919-118">Verwenden Sie ein Attribut, dass denselben Namen wie die Eigenschaft in Kleinbuchstaben hat, um den Wert einer Listenereigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dd919-118">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="dd919-119">Die Attribute `location` und `customlocation` legen z.B. die Werte der Eigenschaften <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> und <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="dd919-119">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>  
  
### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="dd919-120">Schreiben von Ereignisinformationen in das Dateiprotokoll</span><span class="sxs-lookup"><span data-stu-id="dd919-120">To write event information to the file log</span></span>  
  
- <span data-ttu-id="dd919-121">Verwenden Sie die `My.Application.Log.WriteEntry`- oder `My.Application.Log.WriteException`-Methode, um Informationen in das Dateiprotokoll zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="dd919-121">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="dd919-122">Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben von Protokollmeldungen (Visual Basic)](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) und [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="dd919-122">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
     <span data-ttu-id="dd919-123">Nachdem Sie den Dateiprotokolllistener für eine Assembly konfiguriert haben, empfängt er alle Meldungen, die `My.Application.Log` von der betreffenden Assembly schreibt.</span><span class="sxs-lookup"><span data-stu-id="dd919-123">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd919-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd919-124">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="dd919-125">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="dd919-125">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="dd919-126">Vorgehensweise: Protokollieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="dd919-126">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
