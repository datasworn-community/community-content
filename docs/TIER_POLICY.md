# Community Content Tiers

Datasworn Community distinguishes org-supported packages from author-maintained
packages.

## Tier 2: Org-Supported Community Content

Tier 2 packages live in this repo and publish under the
`@datasworn-community` npm scope.

Requirements:

1. The original author agrees to org-supported publication, or the content
   license clearly permits it with attribution.
2. A named maintainer is responsible for keeping the package building against
   current Datasworn schemas.
3. The package passes build and validation checks in CI.
4. Provenance and license details are recorded before publication.
5. The package can be demoted or archived if it loses maintenance.

## Tier 3: Author-Maintained Community Content

Tier 3 packages live in author-owned repositories and publish under an author
scope. They may be listed in the community discovery index, but the org does not
guarantee compatibility or ongoing maintenance.

Listing requirements:

1. Package name and source repository.
2. Author or maintainer contact.
3. Datasworn schema line compatibility.
4. License.
5. Clear "use at your own risk" status.

## Demotion and Archive Policy

A Tier 2 package may be demoted to Tier 3 or archived when:

1. It no longer builds against the current supported schema line.
2. No maintainer is available to review or repair it.
3. License or author-permission concerns make org publication inappropriate.
4. The author prefers to maintain the package independently.

Demotion should preserve attribution, point users to the new author-owned home
when one exists, and remove or disable org publishing for the package.
