---
title: "Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer"
description: "Auflösen mehrdeutiger Zeiten durch den Benutzer"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d6858a5c-02ab-4367-9e08-fa22c051c38d
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ede8d021a4f524cf37f7ad00b6aed89d1b1729f8
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="f7c1b-104">Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="f7c1b-104">How to: let users resolve ambiguous times</span></span>

<span data-ttu-id="f7c1b-105">Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="f7c1b-106">Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="f7c1b-107">Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f7c1b-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="f7c1b-108">Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="f7c1b-109">Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-109">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="f7c1b-110">Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-110">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="f7c1b-111">Dieser Artikel beschreibt, wie Sie eine mehrdeutige Zeit vom Benutzer auflösen lassen.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-111">This article shows how to let a user resolve an ambiguous time.</span></span>

## <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="f7c1b-112">So lassen Sie eine mehrdeutige Zeit vom Benutzer auflösen</span><span class="sxs-lookup"><span data-stu-id="f7c1b-112">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="f7c1b-113">Holen Sie die Datums- und Uhrzeiteingabe vom Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-113">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="f7c1b-114">Rufen Sie die Methode [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) oder [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) auf, um zu bestimmen, ob die Zeit mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-114">Call the [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="f7c1b-115">Ermöglichen Sie dem Benutzer die Auswahl der gewünschten Abweichung.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-115">Let the user select the desired offset.</span></span>

4. <span data-ttu-id="f7c1b-116">Sie erhalten das UTC-Datum und die UTC-Uhrzeit durch Subtrahieren der vom Benutzer ausgewählten Abweichung von der lokalen Zeit.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

5. <span data-ttu-id="f7c1b-117">Rufen Sie die `static`-Methode (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) auf, um die [Kind](xref:System.DateTime.Kind)-Eigenschaft des UTC-Datums- und Uhrzeitwerts auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-117">Call the `static` (`Shared` in Visual Basic ) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="f7c1b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7c1b-118">Example</span></span>

<span data-ttu-id="f7c1b-119">Im folgenden Beispiel wird der Benutzer zur Eingabe eines Datums und einer Uhrzeit aufgefordert. Wenn die Angabe mehrdeutig ist, muss der Benutzer die UTC-Zeit auswählen, die der mehrdeutigen Zeit zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span> <span data-ttu-id="f7c1b-120">Im Beispiel wird ein [DateTime](xref:System.DateTime)-Objekt verwendet. Sie können nach Bedarf stattdessen auch ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt einsetzen.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-120">The example uses a [DateTime](xref:System.DateTime) object; you can substitute a [DateTimeOffset](xref:System.DateTimeOffset) object if desired.</span></span>

```csharp
private void GetUserDateInput()
{
   // Get date and time from user
   DateTime inputDate = GetUserDateTime();
   DateTime utcDate;

   // Exit if date has no significant value
   if (inputDate == DateTime.MinValue) return;

   if (TimeZoneInfo.Local.IsAmbiguousTime(inputDate))
   {
      Console.WriteLine("The date you've entered is ambiguous.");
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:");
      TimeSpan[] offsets = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate);
      for (int ctr = 0; ctr < offsets.Length; ctr++)
      {
         Console.WriteLine("{0}.) {1} hours, {2} minutes", ctr, offsets[ctr].Hours, offsets[ctr].Minutes);
      }
      Console.Write("> ");
      int selection = Convert.ToInt32(Console.ReadLine());

      // Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = DateTime.SpecifyKind(inputDate - offsets[selection], DateTimeKind.Utc);

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());
   }
   else
   {
      utcDate = inputDate.ToUniversalTime();
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());    
   }
}

private DateTime GetUserDateTime() 
{
   bool exitFlag = false;             // flag to exit loop if date is valid
   string dateString;  
   DateTime inputDate = DateTime.MinValue;

   Console.Write("Enter a local date and time: ");
   while (! exitFlag)
   {
      dateString = Console.ReadLine();
      if (dateString.ToUpper() == "E")
         exitFlag = true;

      if (DateTime.TryParse(dateString, out inputDate))
         exitFlag = true;
      else
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ");
   }

   return inputDate;        
}
```

```vb
Private Sub GetUserDateInput()
   ' Get date and time from user
   Dim inputDate As Date = GetUserDateTime()
   Dim utcDate As Date

   ' Exit if date has no significant value
   If inputDate = Date.MinValue Then Exit Sub

   If TimeZoneInfo.Local.IsAmbiguousTime(inputDate) Then
      Console.WriteLine("The date you've entered is ambiguous.")
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:")
      Dim offsets() As TimeSpan = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate)
      For ctr As Integer = 0 to offsets.Length - 1
         Dim zoneDescription As String
         If offsets(ctr).Equals(TimeZoneInfo.Local.BaseUtcOffset) Then 
            zoneDescription = TimeZoneInfo.Local.StandardName
         Else
            zoneDescription = TimeZoneInfo.Local.DaylightName
         End If
         Console.WriteLine("{0}.) {1} hours, {2} minutes ({3})", _
                           ctr, offsets(ctr).Hours, offsets(ctr).Minutes, zoneDescription)
      Next         
      Console.Write("> ")
      Dim selection As Integer = CInt(Console.ReadLine())

      ' Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = Date.SpecifyKind(inputDate - offsets(selection), DateTimeKind.Utc)

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())
   Else
      utcDate = inputDate.ToUniversalTime()
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())    
   End If
End Sub

Private Function GetUserDateTime() As Date
   Dim exitFlag As Boolean = False            ' flag to exit loop if date is valid
   Dim dateString As String 
   Dim inputDate As Date = Date.MinValue

   Console.Write("Enter a local date and time: ")
   Do While Not exitFlag
      dateString = Console.ReadLine()
      If dateString.ToUpper = "E" Then exitFlag = True
      If Date.TryParse(dateString, inputDate) Then
         exitFlag = true
      Else   
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ")
      End If
   Loop

   Return inputDate        
End Function
```

<span data-ttu-id="f7c1b-121">Der Kern des Beispielcodes verwendet ein Array von [TimeSpan](xref:System.TimeSpan)-Objekten, um mögliche Abweichungen der mehrdeutigen Zeit von UTC anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-121">The core of the example code uses an array of [TimeSpan](xref:System.TimeSpan) objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="f7c1b-122">Allerdings sind diese Abweichungen für den Benutzer wahrscheinlich eher unverständlich.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-122">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="f7c1b-123">Um die Bedeutung der Abweichungen zu erläutern, bezeichnet der Code außerdem, ob eine Abweichung die Standardzeit oder die Sommerzeit der lokalen Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-123">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="f7c1b-124">Der Code bestimmt, welche Zeit der Standardzeit und welche Zeit der Sommerzeit entspricht, indem die Abweichung mit dem Wert der [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-124">The code determines which time is standard and which time is daylight by comparing the offset with the value of the [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span> <span data-ttu-id="f7c1b-125">Diese Eigenschaft gibt die Differenz zwischen UTC und der Standardzeit der Zeitzone an.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-125">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="f7c1b-126">In diesem Beispiel erfolgen alle Verweise auf die lokale Zeitzone über die [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local)-Eigenschaft. Die lokale Zeitzone wird nie einer Objektvariablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-126">In this example, all references to the local time zone are made through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="f7c1b-127">Dies ist eine empfohlene Vorgehensweise, da die zwischengespeicherten Daten durch einen weiteren Aufruf möglicherweise gelöscht werden und alle Objekte ihre Gültigkeit verlieren, denen die lokale Zeitzone zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-127">This is a recommended practice because another call could clear the cached data and invalidate any objects that the local time zone is assigned to.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7c1b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7c1b-128">See Also</span></span>

[<span data-ttu-id="f7c1b-129">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="f7c1b-129">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="f7c1b-130">Gewusst wie: Auflösen von mehrdeutigen Zeiten</span><span class="sxs-lookup"><span data-stu-id="f7c1b-130">How to: resolve ambiguous times</span></span>](resolve-ambiguous-times.md)


