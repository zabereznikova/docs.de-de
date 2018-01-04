---
title: DateTime-XAML-Syntax
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3010d3123e78a5e292c5ac78ef4894962fb8f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="74e62-102">DateTime-XAML-Syntax</span><span class="sxs-lookup"><span data-stu-id="74e62-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="74e62-103">Einige Steuerelemente, z. B. <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker>, verfügen über Eigenschaften, mit denen die <xref:System.DateTime> Typ.</span><span class="sxs-lookup"><span data-stu-id="74e62-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="74e62-104">Auch wenn Sie in der Regel ein Anfangsdatum oder eine Uhrzeit für diese Steuerelemente im CodeBehind zur Laufzeit angeben, können Sie ein Anfangsdatum oder eine Uhrzeit in XAML angeben.</span><span class="sxs-lookup"><span data-stu-id="74e62-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="74e62-105">Der WPF XAML-Parser behandelt die Analyse von <xref:System.DateTime> Werte mit einer integrierten XAML-Textsyntax.</span><span class="sxs-lookup"><span data-stu-id="74e62-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="74e62-106">Dieses Thema beschreibt die Einzelheiten der der <xref:System.DateTime> XAML-Textsyntax.</span><span class="sxs-lookup"><span data-stu-id="74e62-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="74e62-107">Verwenden von DateTime-XAML-Syntax</span><span class="sxs-lookup"><span data-stu-id="74e62-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="74e62-108">Das Festlegen von Datumsangaben in XAML ist nicht immer erforderlich und möglicherweise auch nicht erwünscht.</span><span class="sxs-lookup"><span data-stu-id="74e62-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="74e62-109">Beispielsweise können Sie die <xref:System.DateTime.Now%2A?displayProperty=nameWithType> Eigenschaft initialisiert werden, ein Datum zur Laufzeit, oder Sie könnten alle Ihre Datum Korrekturen für einen Kalender in den Code-Behind-basierend auf Benutzereingaben tun.</span><span class="sxs-lookup"><span data-stu-id="74e62-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="74e62-110">Es gibt jedoch Szenarien, in denen Sie möglicherweise zum Hartcodieren von Datumsangaben in einem <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker> in einer Steuerelementvorlage.</span><span class="sxs-lookup"><span data-stu-id="74e62-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="74e62-111">Die <xref:System.DateTime> XAML-Syntax für die folgenden Szenarien verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="74e62-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="74e62-112">DateTime-XAML-Syntax als natives Verhalten</span><span class="sxs-lookup"><span data-stu-id="74e62-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="74e62-113"><xref:System.DateTime>ist eine Klasse, die in den Basisklassenbibliotheken der CLR definiert ist.</span><span class="sxs-lookup"><span data-stu-id="74e62-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="74e62-114">Weil die Basisklassenbibliotheken wie auf den Rest der CLR zu beziehen, ist es nicht möglich, gelten <xref:System.ComponentModel.TypeConverterAttribute> zur Klasse und verwenden Sie einen Typkonverter für das Verarbeiten von Zeichenfolgen in XAML und konvertieren sie <xref:System.DateTime> im Objektmodell zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="74e62-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="74e62-115">Es gibt keine `DateTimeConverter`-Klasse, die das Konvertierungsverhalten ermöglicht. Das in diesem Thema beschriebene Konvertierungsverhalten ist vielmehr ein natives Verhalten im WPF-XAML-Parser.</span><span class="sxs-lookup"><span data-stu-id="74e62-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="74e62-116">Formatzeichenfolgen für DateTime-XAML-Syntax</span><span class="sxs-lookup"><span data-stu-id="74e62-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="74e62-117">Sie können das Format der angeben einer <xref:System.DateTime> mit einer Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="74e62-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="74e62-118">Formatzeichenfolgen formalisieren die Textsyntax, die zum Erstellen eines Werts verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="74e62-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="74e62-119"><xref:System.DateTime>Werte für die vorhandenen WPF-verwenden im Allgemeinen nur, die Bestandteile Datum Steuerelemente <xref:System.DateTime> und nicht die Zeitkomponenten.</span><span class="sxs-lookup"><span data-stu-id="74e62-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="74e62-120">Beim Angeben einer <xref:System.DateTime> in XAML können Sie keines der Formatzeichenfolgen austauschbar.</span><span class="sxs-lookup"><span data-stu-id="74e62-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="74e62-121">Sie können auch Formate und Formatzeichenfolgen verwenden, die in diesem Thema nicht speziell beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="74e62-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="74e62-122">Technisch gesehen der XAML-Code für eine beliebige <xref:System.DateTime> Wert, der angegeben ist, und klicken Sie dann von der WPF XAML-Parser analysiert verwendet einen internen Aufruf <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, daher können Sie eine beliebige Zeichenfolge, die vom akzeptiert <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> für die XAML-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="74e62-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="74e62-123">Weitere Informationen finden Sie unter <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74e62-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74e62-124">Die DateTime XAML-Syntax verwendet immer `en-us` als die <xref:System.Globalization.CultureInfo> für seine systemeigene Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="74e62-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="74e62-125">Dies wird nicht beeinflusst, indem <xref:System.Windows.FrameworkElement.Language%2A> Wert oder `xml:lang` in der XAML-Wert, da typkonvertierung für XAML-Attribut-Ebene ohne dieses Kontexts fungiert.</span><span class="sxs-lookup"><span data-stu-id="74e62-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="74e62-126">Versuchen Sie nicht, die hier angezeigten Formatzeichenfolgen aufgrund von kulturellen Abweichungen, wie z. B. der Reihenfolge von Tag und Monat, zu interpolieren.</span><span class="sxs-lookup"><span data-stu-id="74e62-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="74e62-127">Die hier angezeigten Formatzeichenfolgen sind die genauen Formatzeichenfolgen für die Analyse von XAML unabhängig von anderen Kultureinstellungen.</span><span class="sxs-lookup"><span data-stu-id="74e62-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="74e62-128">Den folgenden Abschnitten werden einige der gängigsten <xref:System.DateTime> Formatzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="74e62-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="74e62-129">Kurzes Datumsmuster („d“)</span><span class="sxs-lookup"><span data-stu-id="74e62-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="74e62-130">Nachstehend sehen Sie das kurze Datumsformat für eine <xref:System.DateTime> in XAML:</span><span class="sxs-lookup"><span data-stu-id="74e62-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="74e62-131">Dies ist die einfachste Möglichkeit, alle erforderlichen Informationen für eine typische Verwendung durch WPF-Steuerelemente anzugeben. Eine Beeinflussung durch versehentliche Zeitzonenverschiebungen gegenüber einer Zeitkomponente ist nicht vorhanden. Daher wird dieses Format anderen Formaten vorgezogen.</span><span class="sxs-lookup"><span data-stu-id="74e62-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="74e62-132">Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="74e62-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="74e62-133">Weitere Informationen finden Sie unter <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74e62-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="74e62-134">Sortierbares DateTime-Muster („s“)</span><span class="sxs-lookup"><span data-stu-id="74e62-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="74e62-135">Das folgende Beispiel zeigt das sortierbare <xref:System.DateTime> Muster in XAML:</span><span class="sxs-lookup"><span data-stu-id="74e62-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="74e62-136">Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):</span><span class="sxs-lookup"><span data-stu-id="74e62-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="74e62-137">RFC1123-Muster („r“)</span><span class="sxs-lookup"><span data-stu-id="74e62-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="74e62-138">Das RFC1123-Muster ist hilfreich, da es sich um eine Zeichenfolgeneingabe aus anderen Datumsgeneratoren handeln könnte, die aus kulturinvarianten Gründen auch das RFC1123-Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="74e62-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="74e62-139">Das folgende Beispiel zeigt das RFC1123 <xref:System.DateTime> Muster in XAML:</span><span class="sxs-lookup"><span data-stu-id="74e62-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="74e62-140">Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):</span><span class="sxs-lookup"><span data-stu-id="74e62-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="74e62-141">Andere Formate und Muster</span><span class="sxs-lookup"><span data-stu-id="74e62-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="74e62-142">Wie zuvor erwähnt eine <xref:System.DateTime> in XAML kann als eine Zeichenfolge, die Komponente ist akzeptabel angegeben werden als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74e62-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="74e62-143">Dies schließt andere formalisierter Formate (z. B. <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), und die Formate ab, die nicht als ein bestimmter formalisiert werden <xref:System.Globalization.DateTimeFormatInfo> Formular.</span><span class="sxs-lookup"><span data-stu-id="74e62-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="74e62-144">Beispielsweise das Formular `YYYY/mm/dd` akzeptabel ist als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74e62-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="74e62-145">In diesem Thema werden nicht alle Formate beschrieben, die funktionieren, sondern das kurze Datumsmuster als Standardverfahren empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="74e62-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e62-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74e62-146">See Also</span></span>  
 [<span data-ttu-id="74e62-147">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="74e62-147">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
