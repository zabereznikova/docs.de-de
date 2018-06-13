---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766932"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="f5446-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="f5446-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="f5446-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="f5446-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="f5446-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f5446-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="f5446-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="f5446-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="f5446-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="f5446-106">Tables</span></span>  
  
-   <span data-ttu-id="f5446-107">Columns</span><span class="sxs-lookup"><span data-stu-id="f5446-107">Columns</span></span>  
  
-   <span data-ttu-id="f5446-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f5446-108">Procedures</span></span>  
  
-   <span data-ttu-id="f5446-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="f5446-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="f5446-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="f5446-110">Catalog</span></span>  
  
-   <span data-ttu-id="f5446-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="f5446-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="f5446-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="f5446-112">Tables</span></span>  
  
|<span data-ttu-id="f5446-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-113">ColumnName</span></span>|<span data-ttu-id="f5446-114">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-115">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-116">String</span></span>|  
|<span data-ttu-id="f5446-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-118">String</span></span>|  
|<span data-ttu-id="f5446-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-119">TABLE_NAME</span></span>|<span data-ttu-id="f5446-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-120">String</span></span>|  
|<span data-ttu-id="f5446-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-121">TABLE_TYPE</span></span>|<span data-ttu-id="f5446-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-122">String</span></span>|  
|<span data-ttu-id="f5446-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-123">TABLE_GUID</span></span>|<span data-ttu-id="f5446-124">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-124">Guid</span></span>|  
|<span data-ttu-id="f5446-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-125">DESCRIPTION</span></span>|<span data-ttu-id="f5446-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-126">String</span></span>|  
|<span data-ttu-id="f5446-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-127">TABLE_PROPID</span></span>|<span data-ttu-id="f5446-128">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-128">Int64</span></span>|  
|<span data-ttu-id="f5446-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-129">DATE_CREATED</span></span>|<span data-ttu-id="f5446-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-130">DateTime</span></span>|  
|<span data-ttu-id="f5446-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-131">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="f5446-133">Columns</span><span class="sxs-lookup"><span data-stu-id="f5446-133">Columns</span></span>  
  
|<span data-ttu-id="f5446-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-134">ColumnName</span></span>|<span data-ttu-id="f5446-135">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-136">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-137">String</span></span>|  
|<span data-ttu-id="f5446-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-139">String</span></span>|  
|<span data-ttu-id="f5446-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-140">TABLE_NAME</span></span>|<span data-ttu-id="f5446-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-141">String</span></span>|  
|<span data-ttu-id="f5446-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-142">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-143">String</span></span>|  
|<span data-ttu-id="f5446-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-144">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-145">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-145">Guid</span></span>|  
|<span data-ttu-id="f5446-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-146">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-147">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-147">Int64</span></span>|  
|<span data-ttu-id="f5446-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-149">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-149">Int64</span></span>|  
|<span data-ttu-id="f5446-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="f5446-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-151">Boolean</span></span>|  
|<span data-ttu-id="f5446-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="f5446-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-153">String</span></span>|  
|<span data-ttu-id="f5446-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f5446-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="f5446-155">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-155">Int64</span></span>|  
|<span data-ttu-id="f5446-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-156">IS_NULLABLE</span></span>|<span data-ttu-id="f5446-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-157">Boolean</span></span>|  
|<span data-ttu-id="f5446-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-158">DATA_TYPE</span></span>|<span data-ttu-id="f5446-159">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-159">Int32</span></span>|  
|<span data-ttu-id="f5446-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-160">TYPE_GUID</span></span>|<span data-ttu-id="f5446-161">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-161">Guid</span></span>|  
|<span data-ttu-id="f5446-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="f5446-163">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-163">Int64</span></span>|  
|<span data-ttu-id="f5446-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="f5446-165">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-165">Int64</span></span>|  
|<span data-ttu-id="f5446-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="f5446-167">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-167">Int32</span></span>|  
|<span data-ttu-id="f5446-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="f5446-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="f5446-169">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-169">Int16</span></span>|  
|<span data-ttu-id="f5446-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="f5446-171">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-171">Int64</span></span>|  
|<span data-ttu-id="f5446-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="f5446-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-173">String</span></span>|  
|<span data-ttu-id="f5446-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="f5446-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-175">String</span></span>|  
|<span data-ttu-id="f5446-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="f5446-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-177">String</span></span>|  
|<span data-ttu-id="f5446-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="f5446-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-179">String</span></span>|  
|<span data-ttu-id="f5446-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="f5446-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-181">String</span></span>|  
|<span data-ttu-id="f5446-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-182">COLLATION_NAME</span></span>|<span data-ttu-id="f5446-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-183">String</span></span>|  
|<span data-ttu-id="f5446-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="f5446-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-185">String</span></span>|  
|<span data-ttu-id="f5446-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="f5446-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-187">String</span></span>|  
|<span data-ttu-id="f5446-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-188">DOMAIN_NAME</span></span>|<span data-ttu-id="f5446-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-189">String</span></span>|  
|<span data-ttu-id="f5446-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-190">DESCRIPTION</span></span>|<span data-ttu-id="f5446-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-191">String</span></span>|  
|<span data-ttu-id="f5446-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="f5446-192">COLUMN_LCID</span></span>|<span data-ttu-id="f5446-193">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-193">Int32</span></span>|  
|<span data-ttu-id="f5446-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="f5446-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="f5446-195">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-195">Int32</span></span>|  
|<span data-ttu-id="f5446-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="f5446-196">COLUMN_SORTID</span></span>|<span data-ttu-id="f5446-197">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-197">Int32</span></span>|  
|<span data-ttu-id="f5446-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="f5446-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="f5446-199">Byte[]</span></span>|  
|<span data-ttu-id="f5446-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="f5446-200">IS_COMPUTED</span></span>|<span data-ttu-id="f5446-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="f5446-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f5446-202">Procedures</span></span>  
  
|<span data-ttu-id="f5446-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-203">ColumnName</span></span>|<span data-ttu-id="f5446-204">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="f5446-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-206">String</span></span>|  
|<span data-ttu-id="f5446-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="f5446-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-208">String</span></span>|  
|<span data-ttu-id="f5446-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="f5446-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-210">String</span></span>|  
|<span data-ttu-id="f5446-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="f5446-212">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-212">Int16</span></span>|  
|<span data-ttu-id="f5446-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f5446-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="f5446-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-214">String</span></span>|  
|<span data-ttu-id="f5446-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-215">DESCRIPTION</span></span>|<span data-ttu-id="f5446-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-216">String</span></span>|  
|<span data-ttu-id="f5446-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-217">DATE_CREATED</span></span>|<span data-ttu-id="f5446-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-218">DateTime</span></span>|  
|<span data-ttu-id="f5446-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-219">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="f5446-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="f5446-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="f5446-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-222">ColumnName</span></span>|<span data-ttu-id="f5446-223">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="f5446-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-225">String</span></span>|  
|<span data-ttu-id="f5446-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="f5446-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-227">String</span></span>|  
|<span data-ttu-id="f5446-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="f5446-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-229">String</span></span>|  
|<span data-ttu-id="f5446-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-230">PARAMETER_NAME</span></span>|<span data-ttu-id="f5446-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-231">String</span></span>|  
|<span data-ttu-id="f5446-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-233">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-233">Int32</span></span>|  
|<span data-ttu-id="f5446-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="f5446-235">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-235">Int32</span></span>|  
|<span data-ttu-id="f5446-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="f5446-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-237">Boolean</span></span>|  
|<span data-ttu-id="f5446-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="f5446-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-239">String</span></span>|  
|<span data-ttu-id="f5446-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-240">IS_NULLABLE</span></span>|<span data-ttu-id="f5446-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-241">Boolean</span></span>|  
|<span data-ttu-id="f5446-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-242">DATA_TYPE</span></span>|<span data-ttu-id="f5446-243">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-243">Int32</span></span>|  
|<span data-ttu-id="f5446-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="f5446-245">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-245">Int64</span></span>|  
|<span data-ttu-id="f5446-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="f5446-247">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-247">Int64</span></span>|  
|<span data-ttu-id="f5446-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="f5446-249">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-249">Int32</span></span>|  
|<span data-ttu-id="f5446-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="f5446-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="f5446-251">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-251">Int16</span></span>|  
|<span data-ttu-id="f5446-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-252">DESCRIPTION</span></span>|<span data-ttu-id="f5446-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-253">String</span></span>|  
|<span data-ttu-id="f5446-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-254">TYPE_NAME</span></span>|<span data-ttu-id="f5446-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-255">String</span></span>|  
|<span data-ttu-id="f5446-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="f5446-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="f5446-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="f5446-258">Catalog</span></span>  
  
|<span data-ttu-id="f5446-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-259">ColumnName</span></span>|<span data-ttu-id="f5446-260">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-261">CATALOG_NAME</span></span>|<span data-ttu-id="f5446-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-262">String</span></span>|  
|<span data-ttu-id="f5446-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-263">DESCRIPTION</span></span>|<span data-ttu-id="f5446-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="f5446-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="f5446-265">Indexes</span></span>  
  
|<span data-ttu-id="f5446-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-266">ColumnName</span></span>|<span data-ttu-id="f5446-267">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-268">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-269">String</span></span>|  
|<span data-ttu-id="f5446-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-271">String</span></span>|  
|<span data-ttu-id="f5446-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-272">TABLE_NAME</span></span>|<span data-ttu-id="f5446-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-273">String</span></span>|  
|<span data-ttu-id="f5446-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-274">INDEX_CATALOG</span></span>|<span data-ttu-id="f5446-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-275">String</span></span>|  
|<span data-ttu-id="f5446-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="f5446-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-277">String</span></span>|  
|<span data-ttu-id="f5446-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-278">INDEX_NAME</span></span>|<span data-ttu-id="f5446-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-279">String</span></span>|  
|<span data-ttu-id="f5446-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="f5446-280">PRIMARY_KEY</span></span>|<span data-ttu-id="f5446-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-281">Boolean</span></span>|  
|<span data-ttu-id="f5446-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="f5446-282">UNIQUE</span></span>|<span data-ttu-id="f5446-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-283">Boolean</span></span>|  
|<span data-ttu-id="f5446-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="f5446-284">CLUSTERED</span></span>|<span data-ttu-id="f5446-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-285">Boolean</span></span>|  
|<span data-ttu-id="f5446-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-286">TYPE</span></span>|<span data-ttu-id="f5446-287">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-287">Int32</span></span>|  
|<span data-ttu-id="f5446-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="f5446-288">FILL_FACTOR</span></span>|<span data-ttu-id="f5446-289">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-289">Int32</span></span>|  
|<span data-ttu-id="f5446-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="f5446-290">INITIAL_SIZE</span></span>|<span data-ttu-id="f5446-291">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-291">Int32</span></span>|  
|<span data-ttu-id="f5446-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="f5446-292">NULLS</span></span>|<span data-ttu-id="f5446-293">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-293">Int32</span></span>|  
|<span data-ttu-id="f5446-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="f5446-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="f5446-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-295">Boolean</span></span>|  
|<span data-ttu-id="f5446-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="f5446-296">AUTO_UPDATE</span></span>|<span data-ttu-id="f5446-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-297">Boolean</span></span>|  
|<span data-ttu-id="f5446-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-298">NULL_COLLATION</span></span>|<span data-ttu-id="f5446-299">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-299">Int32</span></span>|  
|<span data-ttu-id="f5446-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-301">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-301">Int64</span></span>|  
|<span data-ttu-id="f5446-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-302">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-303">String</span></span>|  
|<span data-ttu-id="f5446-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-304">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-305">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-305">Guid</span></span>|  
|<span data-ttu-id="f5446-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-306">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-307">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-307">Int64</span></span>|  
|<span data-ttu-id="f5446-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-308">COLLATION</span></span>|<span data-ttu-id="f5446-309">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-309">Int16</span></span>|  
|<span data-ttu-id="f5446-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="f5446-310">CARDINALITY</span></span>|<span data-ttu-id="f5446-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="f5446-311">Decimal</span></span>|  
|<span data-ttu-id="f5446-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="f5446-312">PAGES</span></span>|<span data-ttu-id="f5446-313">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-313">Int32</span></span>|  
|<span data-ttu-id="f5446-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="f5446-314">FILTER_CONDITION</span></span>|<span data-ttu-id="f5446-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-315">String</span></span>|  
|<span data-ttu-id="f5446-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="f5446-316">INTEGRATED</span></span>|<span data-ttu-id="f5446-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="f5446-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f5446-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="f5446-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="f5446-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="f5446-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="f5446-320">Tables</span></span>  
  
-   <span data-ttu-id="f5446-321">Columns</span><span class="sxs-lookup"><span data-stu-id="f5446-321">Columns</span></span>  
  
-   <span data-ttu-id="f5446-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f5446-322">Procedures</span></span>  
  
-   <span data-ttu-id="f5446-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="f5446-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="f5446-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="f5446-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="f5446-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="f5446-325">Views</span></span>  
  
-   <span data-ttu-id="f5446-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="f5446-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="f5446-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="f5446-327">Tables</span></span>  
  
|<span data-ttu-id="f5446-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-328">ColumnName</span></span>|<span data-ttu-id="f5446-329">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-330">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-331">String</span></span>|  
|<span data-ttu-id="f5446-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-333">String</span></span>|  
|<span data-ttu-id="f5446-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-334">TABLE_NAME</span></span>|<span data-ttu-id="f5446-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-335">String</span></span>|  
|<span data-ttu-id="f5446-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-336">TABLE_TYPE</span></span>|<span data-ttu-id="f5446-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-337">String</span></span>|  
|<span data-ttu-id="f5446-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-338">TABLE_GUID</span></span>|<span data-ttu-id="f5446-339">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-339">Guid</span></span>|  
|<span data-ttu-id="f5446-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-340">DESCRIPTION</span></span>|<span data-ttu-id="f5446-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-341">String</span></span>|  
|<span data-ttu-id="f5446-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-342">TABLE_PROPID</span></span>|<span data-ttu-id="f5446-343">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-343">Int64</span></span>|  
|<span data-ttu-id="f5446-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-344">DATE_CREATED</span></span>|<span data-ttu-id="f5446-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-345">DateTime</span></span>|  
|<span data-ttu-id="f5446-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-346">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="f5446-348">Columns</span><span class="sxs-lookup"><span data-stu-id="f5446-348">Columns</span></span>  
  
|<span data-ttu-id="f5446-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-349">ColumnName</span></span>|<span data-ttu-id="f5446-350">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-351">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-352">String</span></span>|  
|<span data-ttu-id="f5446-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-354">String</span></span>|  
|<span data-ttu-id="f5446-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-355">TABLE_NAME</span></span>|<span data-ttu-id="f5446-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-356">String</span></span>|  
|<span data-ttu-id="f5446-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-357">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-358">String</span></span>|  
|<span data-ttu-id="f5446-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-359">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-360">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-360">Guid</span></span>|  
|<span data-ttu-id="f5446-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-361">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-362">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-362">Int64</span></span>|  
|<span data-ttu-id="f5446-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-364">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-364">Int64</span></span>|  
|<span data-ttu-id="f5446-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="f5446-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-366">Boolean</span></span>|  
|<span data-ttu-id="f5446-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="f5446-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-368">String</span></span>|  
|<span data-ttu-id="f5446-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f5446-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="f5446-370">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-370">Int64</span></span>|  
|<span data-ttu-id="f5446-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-371">IS_NULLABLE</span></span>|<span data-ttu-id="f5446-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-372">Boolean</span></span>|  
|<span data-ttu-id="f5446-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-373">DATA_TYPE</span></span>|<span data-ttu-id="f5446-374">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-374">Int32</span></span>|  
|<span data-ttu-id="f5446-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-375">TYPE_GUID</span></span>|<span data-ttu-id="f5446-376">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-376">Guid</span></span>|  
|<span data-ttu-id="f5446-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="f5446-378">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-378">Int64</span></span>|  
|<span data-ttu-id="f5446-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="f5446-380">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-380">Int64</span></span>|  
|<span data-ttu-id="f5446-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="f5446-382">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-382">Int32</span></span>|  
|<span data-ttu-id="f5446-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="f5446-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="f5446-384">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-384">Int16</span></span>|  
|<span data-ttu-id="f5446-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="f5446-386">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-386">Int64</span></span>|  
|<span data-ttu-id="f5446-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="f5446-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-388">String</span></span>|  
|<span data-ttu-id="f5446-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="f5446-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-390">String</span></span>|  
|<span data-ttu-id="f5446-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="f5446-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-392">String</span></span>|  
|<span data-ttu-id="f5446-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="f5446-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-394">String</span></span>|  
|<span data-ttu-id="f5446-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="f5446-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-396">String</span></span>|  
|<span data-ttu-id="f5446-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-397">COLLATION_NAME</span></span>|<span data-ttu-id="f5446-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-398">String</span></span>|  
|<span data-ttu-id="f5446-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="f5446-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-400">String</span></span>|  
|<span data-ttu-id="f5446-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="f5446-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-402">String</span></span>|  
|<span data-ttu-id="f5446-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-403">DOMAIN_NAME</span></span>|<span data-ttu-id="f5446-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-404">String</span></span>|  
|<span data-ttu-id="f5446-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-405">DESCRIPTION</span></span>|<span data-ttu-id="f5446-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="f5446-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f5446-407">Procedures</span></span>  
  
|<span data-ttu-id="f5446-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-408">ColumnName</span></span>|<span data-ttu-id="f5446-409">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="f5446-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-411">String</span></span>|  
|<span data-ttu-id="f5446-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="f5446-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-413">String</span></span>|  
|<span data-ttu-id="f5446-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="f5446-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-415">String</span></span>|  
|<span data-ttu-id="f5446-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="f5446-417">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-417">Int16</span></span>|  
|<span data-ttu-id="f5446-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f5446-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="f5446-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-419">String</span></span>|  
|<span data-ttu-id="f5446-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-420">DESCRIPTION</span></span>|<span data-ttu-id="f5446-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-421">String</span></span>|  
|<span data-ttu-id="f5446-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-422">DATE_CREATED</span></span>|<span data-ttu-id="f5446-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-423">DateTime</span></span>|  
|<span data-ttu-id="f5446-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-424">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="f5446-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="f5446-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="f5446-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-427">ColumnName</span></span>|<span data-ttu-id="f5446-428">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="f5446-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-430">String</span></span>|  
|<span data-ttu-id="f5446-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="f5446-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-432">String</span></span>|  
|<span data-ttu-id="f5446-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="f5446-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-434">String</span></span>|  
|<span data-ttu-id="f5446-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-435">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-436">String</span></span>|  
|<span data-ttu-id="f5446-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-437">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-438">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-438">Guid</span></span>|  
|<span data-ttu-id="f5446-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-439">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-440">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-440">Int64</span></span>|  
|<span data-ttu-id="f5446-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="f5446-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="f5446-442">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-442">Int64</span></span>|  
|<span data-ttu-id="f5446-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-444">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-444">Int64</span></span>|  
|<span data-ttu-id="f5446-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-445">IS_NULLABLE</span></span>|<span data-ttu-id="f5446-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-446">Boolean</span></span>|  
|<span data-ttu-id="f5446-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-447">DATA_TYPE</span></span>|<span data-ttu-id="f5446-448">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-448">Int32</span></span>|  
|<span data-ttu-id="f5446-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-449">TYPE_GUID</span></span>|<span data-ttu-id="f5446-450">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-450">Guid</span></span>|  
|<span data-ttu-id="f5446-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="f5446-452">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-452">Int64</span></span>|  
|<span data-ttu-id="f5446-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="f5446-454">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-454">Int64</span></span>|  
|<span data-ttu-id="f5446-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="f5446-456">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-456">Int32</span></span>|  
|<span data-ttu-id="f5446-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="f5446-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="f5446-458">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-458">Int16</span></span>|  
|<span data-ttu-id="f5446-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-459">DESCRIPTION</span></span>|<span data-ttu-id="f5446-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-460">String</span></span>|  
|<span data-ttu-id="f5446-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="f5446-461">OVERLOAD</span></span>|<span data-ttu-id="f5446-462">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="f5446-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="f5446-463">Views</span></span>  
  
|<span data-ttu-id="f5446-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-464">ColumnName</span></span>|<span data-ttu-id="f5446-465">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-466">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-467">String</span></span>|  
|<span data-ttu-id="f5446-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-469">String</span></span>|  
|<span data-ttu-id="f5446-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-470">TABLE_NAME</span></span>|<span data-ttu-id="f5446-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-471">String</span></span>|  
|<span data-ttu-id="f5446-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f5446-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="f5446-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-473">String</span></span>|  
|<span data-ttu-id="f5446-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-474">CHECK_OPTION</span></span>|<span data-ttu-id="f5446-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-475">Boolean</span></span>|  
|<span data-ttu-id="f5446-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-476">IS_UPDATABLE</span></span>|<span data-ttu-id="f5446-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-477">Boolean</span></span>|  
|<span data-ttu-id="f5446-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-478">DESCRIPTION</span></span>|<span data-ttu-id="f5446-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-479">String</span></span>|  
|<span data-ttu-id="f5446-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-480">DATE_CREATED</span></span>|<span data-ttu-id="f5446-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-481">DateTime</span></span>|  
|<span data-ttu-id="f5446-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-482">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="f5446-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="f5446-484">Indexes</span></span>  
  
|<span data-ttu-id="f5446-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-485">ColumnName</span></span>|<span data-ttu-id="f5446-486">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-487">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-488">String</span></span>|  
|<span data-ttu-id="f5446-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-490">String</span></span>|  
|<span data-ttu-id="f5446-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-491">TABLE_NAME</span></span>|<span data-ttu-id="f5446-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-492">String</span></span>|  
|<span data-ttu-id="f5446-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-493">INDEX_CATALOG</span></span>|<span data-ttu-id="f5446-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-494">String</span></span>|  
|<span data-ttu-id="f5446-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="f5446-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-496">String</span></span>|  
|<span data-ttu-id="f5446-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-497">INDEX_NAME</span></span>|<span data-ttu-id="f5446-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-498">String</span></span>|  
|<span data-ttu-id="f5446-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="f5446-499">PRIMARY_KEY</span></span>|<span data-ttu-id="f5446-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-500">Boolean</span></span>|  
|<span data-ttu-id="f5446-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="f5446-501">UNIQUE</span></span>|<span data-ttu-id="f5446-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-502">Boolean</span></span>|  
|<span data-ttu-id="f5446-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="f5446-503">CLUSTERED</span></span>|<span data-ttu-id="f5446-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-504">Boolean</span></span>|  
|<span data-ttu-id="f5446-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-505">TYPE</span></span>|<span data-ttu-id="f5446-506">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-506">Int32</span></span>|  
|<span data-ttu-id="f5446-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="f5446-507">FILL_FACTOR</span></span>|<span data-ttu-id="f5446-508">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-508">Int32</span></span>|  
|<span data-ttu-id="f5446-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="f5446-509">INITIAL_SIZE</span></span>|<span data-ttu-id="f5446-510">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-510">Int32</span></span>|  
|<span data-ttu-id="f5446-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="f5446-511">NULLS</span></span>|<span data-ttu-id="f5446-512">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-512">Int32</span></span>|  
|<span data-ttu-id="f5446-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="f5446-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="f5446-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-514">Boolean</span></span>|  
|<span data-ttu-id="f5446-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="f5446-515">AUTO_UPDATE</span></span>|<span data-ttu-id="f5446-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-516">Boolean</span></span>|  
|<span data-ttu-id="f5446-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-517">NULL_COLLATION</span></span>|<span data-ttu-id="f5446-518">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-518">Int32</span></span>|  
|<span data-ttu-id="f5446-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-520">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-520">Int64</span></span>|  
|<span data-ttu-id="f5446-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-521">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-522">String</span></span>|  
|<span data-ttu-id="f5446-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-523">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-524">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-524">Guid</span></span>|  
|<span data-ttu-id="f5446-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-525">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-526">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-526">Int64</span></span>|  
|<span data-ttu-id="f5446-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-527">COLLATION</span></span>|<span data-ttu-id="f5446-528">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-528">Int16</span></span>|  
|<span data-ttu-id="f5446-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="f5446-529">CARDINALITY</span></span>|<span data-ttu-id="f5446-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="f5446-530">Decimal</span></span>|  
|<span data-ttu-id="f5446-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="f5446-531">PAGES</span></span>|<span data-ttu-id="f5446-532">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-532">Int32</span></span>|  
|<span data-ttu-id="f5446-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="f5446-533">FILTER_CONDITION</span></span>|<span data-ttu-id="f5446-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-534">String</span></span>|  
|<span data-ttu-id="f5446-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="f5446-535">INTEGRATED</span></span>|<span data-ttu-id="f5446-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="f5446-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f5446-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="f5446-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="f5446-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="f5446-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="f5446-539">Tables</span></span>  
  
-   <span data-ttu-id="f5446-540">Columns</span><span class="sxs-lookup"><span data-stu-id="f5446-540">Columns</span></span>  
  
-   <span data-ttu-id="f5446-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f5446-541">Procedures</span></span>  
  
-   <span data-ttu-id="f5446-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="f5446-542">Views</span></span>  
  
-   <span data-ttu-id="f5446-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="f5446-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="f5446-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="f5446-544">Tables</span></span>  
  
|<span data-ttu-id="f5446-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-545">ColumnName</span></span>|<span data-ttu-id="f5446-546">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-547">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-548">String</span></span>|  
|<span data-ttu-id="f5446-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-550">String</span></span>|  
|<span data-ttu-id="f5446-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-551">TABLE_NAME</span></span>|<span data-ttu-id="f5446-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-552">String</span></span>|  
|<span data-ttu-id="f5446-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-553">TABLE_TYPE</span></span>|<span data-ttu-id="f5446-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-554">String</span></span>|  
|<span data-ttu-id="f5446-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-555">TABLE_GUID</span></span>|<span data-ttu-id="f5446-556">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-556">Guid</span></span>|  
|<span data-ttu-id="f5446-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-557">DESCRIPTION</span></span>|<span data-ttu-id="f5446-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-558">String</span></span>|  
|<span data-ttu-id="f5446-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-559">TABLE_PROPID</span></span>|<span data-ttu-id="f5446-560">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-560">Int64</span></span>|  
|<span data-ttu-id="f5446-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-561">DATE_CREATED</span></span>|<span data-ttu-id="f5446-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-562">DateTime</span></span>|  
|<span data-ttu-id="f5446-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-563">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="f5446-565">Columns</span><span class="sxs-lookup"><span data-stu-id="f5446-565">Columns</span></span>  
  
|<span data-ttu-id="f5446-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-566">ColumnName</span></span>|<span data-ttu-id="f5446-567">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-568">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-569">String</span></span>|  
|<span data-ttu-id="f5446-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-571">String</span></span>|  
|<span data-ttu-id="f5446-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-572">TABLE_NAME</span></span>|<span data-ttu-id="f5446-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-573">String</span></span>|  
|<span data-ttu-id="f5446-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-574">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-575">String</span></span>|  
|<span data-ttu-id="f5446-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-576">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-577">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-577">Guid</span></span>|  
|<span data-ttu-id="f5446-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-578">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-579">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-579">Int64</span></span>|  
|<span data-ttu-id="f5446-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-581">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-581">Int64</span></span>|  
|<span data-ttu-id="f5446-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="f5446-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-583">Boolean</span></span>|  
|<span data-ttu-id="f5446-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="f5446-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="f5446-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-585">String</span></span>|  
|<span data-ttu-id="f5446-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f5446-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="f5446-587">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-587">Int64</span></span>|  
|<span data-ttu-id="f5446-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-588">IS_NULLABLE</span></span>|<span data-ttu-id="f5446-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-589">Boolean</span></span>|  
|<span data-ttu-id="f5446-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-590">DATA_TYPE</span></span>|<span data-ttu-id="f5446-591">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-591">Int32</span></span>|  
|<span data-ttu-id="f5446-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-592">TYPE_GUID</span></span>|<span data-ttu-id="f5446-593">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-593">Guid</span></span>|  
|<span data-ttu-id="f5446-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="f5446-595">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-595">Int64</span></span>|  
|<span data-ttu-id="f5446-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="f5446-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="f5446-597">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-597">Int64</span></span>|  
|<span data-ttu-id="f5446-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="f5446-599">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-599">Int32</span></span>|  
|<span data-ttu-id="f5446-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="f5446-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="f5446-601">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-601">Int16</span></span>|  
|<span data-ttu-id="f5446-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="f5446-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="f5446-603">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-603">Int64</span></span>|  
|<span data-ttu-id="f5446-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="f5446-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-605">String</span></span>|  
|<span data-ttu-id="f5446-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="f5446-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-607">String</span></span>|  
|<span data-ttu-id="f5446-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="f5446-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-609">String</span></span>|  
|<span data-ttu-id="f5446-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="f5446-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-611">String</span></span>|  
|<span data-ttu-id="f5446-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="f5446-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-613">String</span></span>|  
|<span data-ttu-id="f5446-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-614">COLLATION_NAME</span></span>|<span data-ttu-id="f5446-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-615">String</span></span>|  
|<span data-ttu-id="f5446-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="f5446-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-617">String</span></span>|  
|<span data-ttu-id="f5446-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="f5446-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-619">String</span></span>|  
|<span data-ttu-id="f5446-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-620">DOMAIN_NAME</span></span>|<span data-ttu-id="f5446-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-621">String</span></span>|  
|<span data-ttu-id="f5446-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-622">DESCRIPTION</span></span>|<span data-ttu-id="f5446-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="f5446-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f5446-624">Procedures</span></span>  
  
|<span data-ttu-id="f5446-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-625">ColumnName</span></span>|<span data-ttu-id="f5446-626">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="f5446-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-628">String</span></span>|  
|<span data-ttu-id="f5446-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="f5446-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-630">String</span></span>|  
|<span data-ttu-id="f5446-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="f5446-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-632">String</span></span>|  
|<span data-ttu-id="f5446-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="f5446-634">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-634">Int16</span></span>|  
|<span data-ttu-id="f5446-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f5446-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="f5446-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-636">String</span></span>|  
|<span data-ttu-id="f5446-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-637">DESCRIPTION</span></span>|<span data-ttu-id="f5446-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-638">String</span></span>|  
|<span data-ttu-id="f5446-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-639">DATE_CREATED</span></span>|<span data-ttu-id="f5446-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-640">DateTime</span></span>|  
|<span data-ttu-id="f5446-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-641">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="f5446-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="f5446-643">Views</span></span>  
  
|<span data-ttu-id="f5446-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-644">ColumnName</span></span>|<span data-ttu-id="f5446-645">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-646">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-647">String</span></span>|  
|<span data-ttu-id="f5446-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-649">String</span></span>|  
|<span data-ttu-id="f5446-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-650">TABLE_NAME</span></span>|<span data-ttu-id="f5446-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-651">String</span></span>|  
|<span data-ttu-id="f5446-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f5446-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="f5446-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-653">String</span></span>|  
|<span data-ttu-id="f5446-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-654">CHECK_OPTION</span></span>|<span data-ttu-id="f5446-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-655">Boolean</span></span>|  
|<span data-ttu-id="f5446-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="f5446-656">IS_UPDATABLE</span></span>|<span data-ttu-id="f5446-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-657">Boolean</span></span>|  
|<span data-ttu-id="f5446-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5446-658">DESCRIPTION</span></span>|<span data-ttu-id="f5446-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-659">String</span></span>|  
|<span data-ttu-id="f5446-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="f5446-660">DATE_CREATED</span></span>|<span data-ttu-id="f5446-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-661">DateTime</span></span>|  
|<span data-ttu-id="f5446-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="f5446-662">DATE_MODIFIED</span></span>|<span data-ttu-id="f5446-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="f5446-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="f5446-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="f5446-664">Indexes</span></span>  
  
|<span data-ttu-id="f5446-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f5446-665">ColumnName</span></span>|<span data-ttu-id="f5446-666">DataType</span><span class="sxs-lookup"><span data-stu-id="f5446-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="f5446-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-667">TABLE_CATALOG</span></span>|<span data-ttu-id="f5446-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-668">String</span></span>|  
|<span data-ttu-id="f5446-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="f5446-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-670">String</span></span>|  
|<span data-ttu-id="f5446-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-671">TABLE_NAME</span></span>|<span data-ttu-id="f5446-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-672">String</span></span>|  
|<span data-ttu-id="f5446-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5446-673">INDEX_CATALOG</span></span>|<span data-ttu-id="f5446-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-674">String</span></span>|  
|<span data-ttu-id="f5446-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5446-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="f5446-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-676">String</span></span>|  
|<span data-ttu-id="f5446-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-677">INDEX_NAME</span></span>|<span data-ttu-id="f5446-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-678">String</span></span>|  
|<span data-ttu-id="f5446-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="f5446-679">PRIMARY_KEY</span></span>|<span data-ttu-id="f5446-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-680">Boolean</span></span>|  
|<span data-ttu-id="f5446-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="f5446-681">UNIQUE</span></span>|<span data-ttu-id="f5446-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-682">Boolean</span></span>|  
|<span data-ttu-id="f5446-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="f5446-683">CLUSTERED</span></span>|<span data-ttu-id="f5446-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-684">Boolean</span></span>|  
|<span data-ttu-id="f5446-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="f5446-685">TYPE</span></span>|<span data-ttu-id="f5446-686">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-686">Int32</span></span>|  
|<span data-ttu-id="f5446-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="f5446-687">FILL_FACTOR</span></span>|<span data-ttu-id="f5446-688">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-688">Int32</span></span>|  
|<span data-ttu-id="f5446-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="f5446-689">INITIAL_SIZE</span></span>|<span data-ttu-id="f5446-690">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-690">Int32</span></span>|  
|<span data-ttu-id="f5446-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="f5446-691">NULLS</span></span>|<span data-ttu-id="f5446-692">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-692">Int32</span></span>|  
|<span data-ttu-id="f5446-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="f5446-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="f5446-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-694">Boolean</span></span>|  
|<span data-ttu-id="f5446-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="f5446-695">AUTO_UPDATE</span></span>|<span data-ttu-id="f5446-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="f5446-696">Boolean</span></span>|  
|<span data-ttu-id="f5446-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-697">NULL_COLLATION</span></span>|<span data-ttu-id="f5446-698">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-698">Int32</span></span>|  
|<span data-ttu-id="f5446-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="f5446-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="f5446-700">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-700">Int64</span></span>|  
|<span data-ttu-id="f5446-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f5446-701">COLUMN_NAME</span></span>|<span data-ttu-id="f5446-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-702">String</span></span>|  
|<span data-ttu-id="f5446-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="f5446-703">COLUMN_GUID</span></span>|<span data-ttu-id="f5446-704">Guid</span><span class="sxs-lookup"><span data-stu-id="f5446-704">Guid</span></span>|  
|<span data-ttu-id="f5446-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="f5446-705">COLUMN_PROPID</span></span>|<span data-ttu-id="f5446-706">Int64</span><span class="sxs-lookup"><span data-stu-id="f5446-706">Int64</span></span>|  
|<span data-ttu-id="f5446-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="f5446-707">COLLATION</span></span>|<span data-ttu-id="f5446-708">Int16</span><span class="sxs-lookup"><span data-stu-id="f5446-708">Int16</span></span>|  
|<span data-ttu-id="f5446-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="f5446-709">CARDINALITY</span></span>|<span data-ttu-id="f5446-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="f5446-710">Decimal</span></span>|  
|<span data-ttu-id="f5446-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="f5446-711">PAGES</span></span>|<span data-ttu-id="f5446-712">Int32</span><span class="sxs-lookup"><span data-stu-id="f5446-712">Int32</span></span>|  
|<span data-ttu-id="f5446-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="f5446-713">FILTER_CONDITION</span></span>|<span data-ttu-id="f5446-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5446-714">String</span></span>|  
|<span data-ttu-id="f5446-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="f5446-715">INTEGRATED</span></span>|<span data-ttu-id="f5446-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5446-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5446-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5446-717">See Also</span></span>  
 [<span data-ttu-id="f5446-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f5446-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
