---
title: Nicht unterstützte APIs in .NET Core und .NET 5 (und höher)
titleSuffix: ''
description: Hier erfahren Sie, welche .NET-APIs in .NET Core und .NET 5.0 und höheren Versionen immer eine Ausnahme auslösen.
ms.date: 10/13/2020
ms.openlocfilehash: 51d73557a48910d9cb1c4d3cdced34dfe4d849d8
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329780"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="d1905-103">APIs, die in .NET Core und .NET 5 und höher immer Ausnahmen auslösen</span><span class="sxs-lookup"><span data-stu-id="d1905-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="d1905-104">Die folgenden APIs lösen in .NET 5.0 und höheren Versionen (einschließlich aller .NET Core-Versionen) auf allen oder einer Teilmenge aller Plattformen immer eine <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="d1905-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="d1905-105">In diesem Artikel werden die betroffenen APIs nach Namespace organisiert.</span><span class="sxs-lookup"><span data-stu-id="d1905-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d1905-106">Dies ist nicht die endgültige Fassung dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="d1905-106">This article is a work-in-progress.</span></span> <span data-ttu-id="d1905-107">Er enthält keine vollständige Liste der APIs, die Ausnahmen in .NET 5 und höher auslösen.</span><span class="sxs-lookup"><span data-stu-id="d1905-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="d1905-108">In diesem Artikel sind die expliziten Schnittstellenimplementierungen für die binäre Serialisierung, die in .NET 5 und höher eine Ausnahme auslösen, nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1905-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="d1905-109">Weitere Informationen finden Sie unter [Binäre Serialisierung](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="d1905-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="d1905-110">System</span><span class="sxs-lookup"><span data-stu-id="d1905-110">System</span></span>

| <span data-ttu-id="d1905-111">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-111">Member</span></span> | <span data-ttu-id="d1905-112">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-113">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="d1905-114">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="d1905-115">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="d1905-116">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-117">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="d1905-118">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="d1905-119">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="d1905-120">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-121">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="d1905-122">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="d1905-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="d1905-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="d1905-124">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-124">Member</span></span> | <span data-ttu-id="d1905-125">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-126">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-127">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-128">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="d1905-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="d1905-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="d1905-130">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-130">Member</span></span> | <span data-ttu-id="d1905-131">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-132">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-133">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d1905-134">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="d1905-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="d1905-135">System.Configuration</span></span>

| <span data-ttu-id="d1905-136">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-136">Member</span></span> | <span data-ttu-id="d1905-137">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="d1905-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="d1905-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="d1905-139">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="d1905-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="d1905-140">System.Console</span></span>

| <span data-ttu-id="d1905-141">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-141">Member</span></span> | <span data-ttu-id="d1905-142">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="d1905-143">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-143">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-145">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-145">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-147">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-147">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-149">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-149">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="d1905-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="d1905-151">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-152">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-153">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-154">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-154">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-155"><xref:System.Console.Title?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="d1905-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="d1905-156">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-156">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-158">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-158">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-160">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-160">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-162">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-162">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-164">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="d1905-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="d1905-165">System.Data.Common</span></span>

| <span data-ttu-id="d1905-166">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-166">Member</span></span> | <span data-ttu-id="d1905-167">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="d1905-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (löst <xref:System.NotSupportedException> aus)</span><span class="sxs-lookup"><span data-stu-id="d1905-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="d1905-169">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="d1905-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="d1905-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="d1905-171">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-171">Member</span></span> | <span data-ttu-id="d1905-172">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="d1905-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-174">Linux</span><span class="sxs-lookup"><span data-stu-id="d1905-174">Linux</span></span> |
| <span data-ttu-id="d1905-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-176">Linux</span><span class="sxs-lookup"><span data-stu-id="d1905-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="d1905-177">macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="d1905-178">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-179">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="d1905-180">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="d1905-181">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="d1905-182">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="d1905-183">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-183">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-185">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-185">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="d1905-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="d1905-187">macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-187">macOS</span></span> |
| <span data-ttu-id="d1905-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-189">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="d1905-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="d1905-190">System.IO</span></span>

| <span data-ttu-id="d1905-191">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-191">Member</span></span> | <span data-ttu-id="d1905-192">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-193">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-194">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="d1905-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="d1905-195">System.IO.Pipes</span></span>

| <span data-ttu-id="d1905-196">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-196">Member</span></span> | <span data-ttu-id="d1905-197">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="d1905-198">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="d1905-199">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="d1905-200">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="d1905-201">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-201">Linux and macOS</span></span> |
| <span data-ttu-id="d1905-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-203">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="d1905-204">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="d1905-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="d1905-205">System.Media</span></span>

| <span data-ttu-id="d1905-206">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-206">Member</span></span> | <span data-ttu-id="d1905-207">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-208">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="d1905-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="d1905-209">System.Net</span></span>

| <span data-ttu-id="d1905-210">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-210">Member</span></span> | <span data-ttu-id="d1905-211">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="d1905-212">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="d1905-213">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-214">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-215">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-216">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-217">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-218">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-219">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-220">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-221">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-222">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="d1905-223">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-224">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-225">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-226">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-227">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-228">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="d1905-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="d1905-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="d1905-230">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-230">Member</span></span> | <span data-ttu-id="d1905-231">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="d1905-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="d1905-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="d1905-233">System.Net.Sockets</span></span>

| <span data-ttu-id="d1905-234">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-234">Member</span></span> | <span data-ttu-id="d1905-235">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="d1905-236">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="d1905-237">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="d1905-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="d1905-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="d1905-239">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-239">Member</span></span> | <span data-ttu-id="d1905-240">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="d1905-241">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="d1905-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="d1905-242">System.Reflection</span></span>

| <span data-ttu-id="d1905-243">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-243">Member</span></span> | <span data-ttu-id="d1905-244">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-245">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-246">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-247">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d1905-248">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="d1905-249">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-250">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="d1905-251">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="d1905-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="d1905-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="d1905-253">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-253">Member</span></span> | <span data-ttu-id="d1905-254">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="d1905-255">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="d1905-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="d1905-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="d1905-257">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-257">Member</span></span> | <span data-ttu-id="d1905-258">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d1905-259">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="d1905-260">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="d1905-261">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="d1905-262">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-263">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="d1905-264">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="d1905-265">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="d1905-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="d1905-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="d1905-267">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-267">Member</span></span> | <span data-ttu-id="d1905-268">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="d1905-269">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="d1905-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="d1905-270">System.Security</span></span>

| <span data-ttu-id="d1905-271">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-271">Member</span></span> | <span data-ttu-id="d1905-272">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="d1905-273">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="d1905-274">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-275">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="d1905-276">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="d1905-277">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="d1905-278">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="d1905-279">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="d1905-280">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="d1905-281">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="d1905-282">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="d1905-283">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="d1905-284">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="d1905-285">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="d1905-286">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="d1905-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="d1905-287">System.Security.Claims</span></span>

| <span data-ttu-id="d1905-288">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-288">Member</span></span> | <span data-ttu-id="d1905-289">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-290">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-291">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="d1905-292">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-293">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-294">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="d1905-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="d1905-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="d1905-296">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-296">Member</span></span> | <span data-ttu-id="d1905-297">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-298">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="d1905-299">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="d1905-300">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="d1905-301">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="d1905-302">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="d1905-303">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="d1905-304">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="d1905-305">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="d1905-306">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="d1905-307">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="d1905-308">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="d1905-309">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="d1905-310">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="d1905-311">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="d1905-312">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="d1905-313">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-314">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-315">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-316">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-317">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="d1905-318">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-319">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-320">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-321">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1905-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-322">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-323">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="d1905-324">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="d1905-325">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="d1905-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="d1905-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="d1905-327">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-327">Member</span></span> | <span data-ttu-id="d1905-328">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="d1905-329">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="d1905-330">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="d1905-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="d1905-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="d1905-332">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-332">Member</span></span> | <span data-ttu-id="d1905-333">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-334">All</span><span class="sxs-lookup"><span data-stu-id="d1905-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-335">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-336">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-336">All</span></span> |
| <span data-ttu-id="d1905-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="d1905-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="d1905-338">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="d1905-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="d1905-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="d1905-340">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-340">Member</span></span> | <span data-ttu-id="d1905-341">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-342">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="d1905-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="d1905-343">System.Security.Policy</span></span>

| <span data-ttu-id="d1905-344">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-344">Member</span></span> | <span data-ttu-id="d1905-345">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-346">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="d1905-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="d1905-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="d1905-348">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-348">Member</span></span> | <span data-ttu-id="d1905-349">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="d1905-350">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="d1905-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="d1905-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="d1905-352">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-352">Member</span></span> | <span data-ttu-id="d1905-353">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-354">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="d1905-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="d1905-355">System.Threading</span></span>

| <span data-ttu-id="d1905-356">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-356">Member</span></span> | <span data-ttu-id="d1905-357">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-358">All</span><span class="sxs-lookup"><span data-stu-id="d1905-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="d1905-359">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="d1905-360">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="d1905-361">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="d1905-362">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="d1905-363">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="d1905-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d1905-364">System.Xml</span></span>

| <span data-ttu-id="d1905-365">Member</span><span class="sxs-lookup"><span data-stu-id="d1905-365">Member</span></span> | <span data-ttu-id="d1905-366">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d1905-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="d1905-367">All</span><span class="sxs-lookup"><span data-stu-id="d1905-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="d1905-368">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="d1905-369">Alle</span><span class="sxs-lookup"><span data-stu-id="d1905-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="d1905-370">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1905-370">See also</span></span>

- [<span data-ttu-id="d1905-371">Breaking Changes für die Migration von .NET Framework zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1905-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="d1905-372">Binäre Serialisierung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1905-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="d1905-373">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="d1905-373">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
