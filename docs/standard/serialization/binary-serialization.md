---
title: Binäre Serialisierung
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401268"
---
# <a name="binary-serialization"></a><span data-ttu-id="8c452-102">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8c452-102">Binary serialization</span></span>

<span data-ttu-id="8c452-103">Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c452-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="8c452-104">Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8c452-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="8c452-105">Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.</span><span class="sxs-lookup"><span data-stu-id="8c452-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="8c452-106">Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="8c452-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="8c452-107">Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben.</span><span class="sxs-lookup"><span data-stu-id="8c452-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="8c452-108">Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8c452-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="8c452-109">In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="8c452-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="8c452-110">Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="8c452-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="8c452-111">Die binäre Serialisierung ermöglicht das Ändern privater Elemente innerhalb eines Objekts und damit das Ändern des Status dieses Objekts.</span><span class="sxs-lookup"><span data-stu-id="8c452-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="8c452-112">Aus diesem Grund werden andere Serialisierungsframeworks wie <xref:System.Text.Json?displayProperty=fullName>empfohlen, die auf der öffentlichen API-Oberfläche ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c452-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="8c452-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8c452-113">.NET Core</span></span>

<span data-ttu-id="8c452-114">.NET Core unterstützt die binäre Serialisierung für eine Teilmenge von Typen.</span><span class="sxs-lookup"><span data-stu-id="8c452-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="8c452-115">Sie können die Liste der unterstützten Typen im folgenden Abschnitt [Serializable types](#serializable-types) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c452-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="8c452-116">Die aufgeführten Typen sind garantiert zwischen .NET Framework 4.5.1 und neueren Versionen sowie zwischen .NET Core 2.0 und neueren Versionen serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="8c452-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="8c452-117">Andere .NET-Implementierungen, z. B. Mono, werden nicht offiziell unterstützt, sollten aber auch funktionieren.</span><span class="sxs-lookup"><span data-stu-id="8c452-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="8c452-118">Serialisierbare Typen</span><span class="sxs-lookup"><span data-stu-id="8c452-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="8c452-119">type</span><span class="sxs-lookup"><span data-stu-id="8c452-119">Type</span></span> | <span data-ttu-id="8c452-120">Notizen</span><span class="sxs-lookup"><span data-stu-id="8c452-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="8c452-121">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="8c452-122">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-123">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="8c452-124">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-125">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-126">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="8c452-127">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="8c452-128">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="8c452-129">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="8c452-130">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="8c452-131">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="8c452-132">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="8c452-133">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-134">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="8c452-135">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-136">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="8c452-137">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="8c452-138">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="8c452-139">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="8c452-140">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="8c452-141">Die Serialisierung von .NET Framework in .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c452-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="8c452-142">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="8c452-143">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="8c452-144">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-145">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="8c452-146">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="8c452-147">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-148">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="8c452-149">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="8c452-150">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="8c452-151">Beginnend in .NET Core 2.0.2 und neueren Versionen.</span><span class="sxs-lookup"><span data-stu-id="8c452-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="8c452-152">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="8c452-153">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="8c452-154">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="8c452-155">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="8c452-156">Wenn Sie `RemotingFormat` `SerializationFormat.Binary`auf festlegen, kann es nur mit .NET Core 2.1 und neueren Versionen ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="8c452-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="8c452-157">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="8c452-158">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="8c452-159">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="8c452-160">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="8c452-161">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-162">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="8c452-163">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-164">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="8c452-165">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-166">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="8c452-167">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="8c452-168">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="8c452-169">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="8c452-170">Serialisierung von .NET Framework in .NET Core wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="8c452-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="8c452-171">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="8c452-172">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="8c452-173">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="8c452-174">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="8c452-175">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="8c452-176">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="8c452-177">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-178">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-179">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="8c452-180">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="8c452-181">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-182">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="8c452-183">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="8c452-184">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="8c452-185">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="8c452-186">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="8c452-187">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-188">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="8c452-189">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="8c452-190">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-191">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-192">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="8c452-193">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-194">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-195">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="8c452-196">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-197">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="8c452-198">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-199">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="8c452-200">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-201">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="8c452-202">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-203">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="8c452-204">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-205">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="8c452-206">Beginnend in .NET Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="8c452-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="8c452-207">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="8c452-208">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="8c452-209">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-210">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="8c452-211">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-212">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="8c452-213">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="8c452-214">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="8c452-215">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-216">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="8c452-217">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="8c452-218">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="8c452-219">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="8c452-220">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="8c452-221">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="8c452-222">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="8c452-223">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="8c452-224">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="8c452-225">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-226">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="8c452-227">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="8c452-228">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="8c452-229">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="8c452-230">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="8c452-231">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="8c452-232">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="8c452-233">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-234">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="8c452-235">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="8c452-236">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="8c452-237">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="8c452-238">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="8c452-239">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-240">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="8c452-241">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-242">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="8c452-243">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="8c452-244">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="8c452-245">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="8c452-246">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-247">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-248">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="8c452-249">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-250">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="8c452-251">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="8c452-252">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="8c452-253">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-254">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="8c452-255">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="8c452-256">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="8c452-257">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="8c452-258">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="8c452-259">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="8c452-260">Die Serialisierung von .NET Framework in .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c452-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="8c452-261">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-262">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="8c452-263">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="8c452-264">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="8c452-265">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-266">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="8c452-267">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="8c452-268">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="8c452-269">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="8c452-270">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="8c452-271">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="8c452-272">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="8c452-273">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="8c452-274">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="8c452-275">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-276">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="8c452-277">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-278">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="8c452-279">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="8c452-280">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-281">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="8c452-282">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-283">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="8c452-284">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-285">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="8c452-286">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="8c452-287">Begrenzte Serialisierungsdaten.</span><span class="sxs-lookup"><span data-stu-id="8c452-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-288">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="8c452-289">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="8c452-290">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="8c452-291">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="8c452-292">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="8c452-293">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="8c452-294">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="8c452-295">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="8c452-296">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="8c452-297">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-298">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="8c452-299">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="8c452-300">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="8c452-301">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="8c452-302">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="8c452-303">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-304">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="8c452-305">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="8c452-306">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-307">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="8c452-308">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="8c452-309">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-310">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-311">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="8c452-312">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-313">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="8c452-314">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="8c452-315">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-316">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="8c452-317">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="8c452-318">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="8c452-319">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="8c452-320">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="8c452-321">Nicht serialisierbar in .NET Framework 4.7 und früheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="8c452-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="8c452-322">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="8c452-323">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="8c452-324">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="8c452-325">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="8c452-326">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="8c452-327">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="8c452-328">Beginnend in .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="8c452-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8c452-329">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c452-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="8c452-330">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8c452-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="8c452-331">[XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="8c452-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="8c452-332">Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="8c452-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="8c452-333">[Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="8c452-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="8c452-334">Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.</span><span class="sxs-lookup"><span data-stu-id="8c452-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="8c452-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8c452-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="8c452-336">Beschreibt die verschiedenen Methoden, die in .NET Framework für Die Remotekommunikation beginnen.</span><span class="sxs-lookup"><span data-stu-id="8c452-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="8c452-337">[ERSTELLTe XML-Webdienste mit ASP.NET- und XML-Webdienstclients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8c452-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="8c452-338">Artikel, in denen beschrieben und erläutert wird, wie XML-Webdienste mithilfe von ASP.NET erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8c452-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
