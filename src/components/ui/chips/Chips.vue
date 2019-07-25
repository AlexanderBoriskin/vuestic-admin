<template>
  <div class="tags">
    <div class="row">
      <div class="flex xs12">
        <va-card :title="$t('chips.chips')">
          <div class="row mb-3">
            <va-chip>
              Success chip
            </va-chip>
            <va-chip color="info">
              Info chip
            </va-chip>
            <va-chip color="danger">
              Danger chip
            </va-chip>
            <va-chip color="warning">
              Warning chip
            </va-chip>
            <va-chip color="gray">
              Gray chip
            </va-chip>
            <va-chip color="dark">
              Dark chip
            </va-chip>
          </div>
          <div class="row">
            <va-chip outline>
              Success chip
            </va-chip>
            <va-chip outline color="info">
              Info chip
            </va-chip>
            <va-chip outline color="danger">
              Danger chip
            </va-chip>
            <va-chip outline color="warning">
              Warning chip
            </va-chip>
            <va-chip outline color="gray">
              Gray chip
            </va-chip>
            <va-chip outline color="dark">
              Dark chip
            </va-chip>
          </div>
        </va-card>
      </div>

      <div class="flex xs12">
        <va-card :title="$t('chips.countBadges')">
          <div class="row mt-1 mb-4">
            <va-count-badge class="mr-4" :number="1">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="12">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="999">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="123456">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="123456789">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="12345678912345">Statuses</va-count-badge>
          </div>
          <div class="row">
            <va-count-badge class="mr-4" :number="5" color="info">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="5" color="warning">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="5" color="success">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="5" color="gray">Statuses</va-count-badge>
            <va-count-badge class="mr-4" :number="5" color="dark">Statuses</va-count-badge>
          </div>
        </va-card>
      </div>

      <div class="flex xs12">
        <va-card :title="$t('chips.badges')">
          <div class="row mb-3">
            <va-badge>
              Paid
            </va-badge>
            <va-badge color="info">
              Info
            </va-badge>
            <va-badge color="danger">
              Danger
            </va-badge>
            <va-badge color="warning">
              On Hold
            </va-badge>
            <va-badge color="gray">
              Processing
            </va-badge>
            <va-badge color="dark">
              New Label
            </va-badge>
          </div>
          <div class="row">
            <va-badge outline>
              Paid
            </va-badge>
            <va-badge outline color="info">
              Info
            </va-badge>
            <va-badge outline color="danger">
              Danger
            </va-badge>
            <va-badge outline color="warning">
              On Hold
            </va-badge>
            <va-badge outline color="gray">
              Processing
            </va-badge>
            <va-badge outline color="dark">
              New Label
            </va-badge>
          </div>
        </va-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'tags',
}
</script>
