---
title: 'Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: 6e83f8450ca7be8a2dcd5ff43eab3dd2ec0d2f1b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410061"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="70f0d-102">Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70f0d-102">How to: Write Event Information to a Text File (Visual Basic)</span></span>

<span data-ttu-id="70f0d-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="70f0d-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="70f0d-104">Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry`-Methode zum Protokollieren von Nachverfolgungsinformationen, um eine Datei zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="70f0d-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>

### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="70f0d-105">Hinzufügen und Konfigurieren des Dateiprotokolllisteners</span><span class="sxs-lookup"><span data-stu-id="70f0d-105">To add and configure the file log listener</span></span>

1. <span data-ttu-id="70f0d-106">Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="70f0d-106">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="70f0d-107">\- oder -</span><span class="sxs-lookup"><span data-stu-id="70f0d-107">\- or -</span></span>

     <span data-ttu-id="70f0d-108">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="70f0d-108">If there is no app.config file:</span></span>

    1. <span data-ttu-id="70f0d-109">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="70f0d-109">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="70f0d-110">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="70f0d-110">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="70f0d-111">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="70f0d-111">Click **Add**.</span></span>

2. <span data-ttu-id="70f0d-112">Suchen Sie den Abschnitt `<listeners>` in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="70f0d-112">Locate the `<listeners>` section in the application configuration file.</span></span>

     <span data-ttu-id="70f0d-113">Sie finden den Abschnitt \<listeners> im \<source> -Abschnitt mit dem Namensattribut "DefaultSource", der in den \<system.diagnostics> -Abschnitt verschachtelt ist, der seinerseits in den \<configuration> -Abschnitt der obersten Ebene verschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="70f0d-113">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>

3. <span data-ttu-id="70f0d-114">Fügen Sie dem `<listeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="70f0d-114">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="FileLogListener" />
    ```

4. <span data-ttu-id="70f0d-115">Machen Sie den Abschnitt `<sharedListeners>` im Abschnitt `<system.diagnostics>`, der sich unter dem Abschnitt der höchsten Ebene `<configuration>` befindet.</span><span class="sxs-lookup"><span data-stu-id="70f0d-115">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="70f0d-116">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="70f0d-116">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="FileLogListener"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
              PublicKeyToken=b03f5f7f11d50a3a"
        initializeData="FileLogListenerWriter"
        location="Custom"
        customlocation="c:\temp\" />
    ```

     <span data-ttu-id="70f0d-117">Ändern Sie den Wert des `customlocation`-Attributs in das Protokollverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="70f0d-117">Change the value of the `customlocation` attribute to the log directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70f0d-118">Verwenden Sie ein Attribut, dass denselben Namen wie die Eigenschaft in Kleinbuchstaben hat, um den Wert einer Listenereigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="70f0d-118">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="70f0d-119">Die Attribute `location` und `customlocation` legen z.B. die Werte der Eigenschaften <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> und <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="70f0d-119">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>

### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="70f0d-120">Schreiben von Ereignisinformationen in das Dateiprotokoll</span><span class="sxs-lookup"><span data-stu-id="70f0d-120">To write event information to the file log</span></span>

<span data-ttu-id="70f0d-121">Verwenden Sie die `My.Application.Log.WriteEntry`- oder `My.Application.Log.WriteException`-Methode, um Informationen in das Dateiprotokoll zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="70f0d-121">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="70f0d-122">Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben von Protokollmeldungen](how-to-write-log-messages.md) und [Vorgehensweise: Protokollieren von Ausnahmen](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="70f0d-122">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="70f0d-123">Nachdem Sie den Dateiprotokolllistener für eine Assembly konfiguriert haben, empfängt er alle Meldungen, die `My.Application.Log` von der betreffenden Assembly schreibt.</span><span class="sxs-lookup"><span data-stu-id="70f0d-123">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="70f0d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70f0d-124">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="70f0d-125">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="70f0d-125">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="70f0d-126">Gewusst wie: Protokollieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="70f0d-126">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
