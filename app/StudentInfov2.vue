<template>
  <div class="min-h-screen">
    <div class="px-12 pt-12">
      <div class="flex items-center justify-between mb-4">
        <h1 class="text-2xl font-semibold text-gray-700">{{ tabTitles[activeTab] }}</h1>
        <div class="flex gap-2">
          <Button icon="pi pi-pencil" label="Edit" class="p-button-outlined p-button-sm header-btn-edit" />
          <Button icon="pi pi-print" class="p-button-outlined p-button-sm header-btn-print" />
          <Button icon="pi pi-trash" class="p-button-outlined p-button-danger p-button-sm header-btn-delete" />
        </div>
      </div>
      <nav class="flex gap-2 border-b border-gray-200 mb-8 text-sm">
        <Button icon="pi pi-user" label="Personal Info" class="p-button-text tab-btn" :class="{ 'tab-active': activeTab === 'personal' }" style="border-radius:0;" @click="changeTab('personal')" />
        <Button icon="pi pi-map-marker" label="Services Recommended" class="p-button-text tab-btn" :class="{ 'tab-active': activeTab === 'services' }" style="border-radius:0;" @click="changeTab('services')" />
        <Button icon="pi pi-file" label="Documents" class="p-button-text tab-btn" :class="{ 'tab-active': activeTab === 'documents' }" style="border-radius:0;" @click="changeTab('documents')" />
        <Button icon="pi pi-comment" label="Notes" class="p-button-text tab-btn" :class="{ 'tab-active': activeTab === 'notes' }" style="border-radius:0;" @click="changeTab('notes')" />
        <Button icon="pi pi-users" label="Staffs" class="p-button-text tab-btn" :class="{ 'tab-active': activeTab === 'staffs' }" style="border-radius:0;" @click="changeTab('staffs')" />
        <Button icon="pi pi-calendar" label="Schedules" class="p-button-text tab-btn" :class="{ 'tab-active': activeTab === 'schedules' }" style="border-radius:0;" @click="changeTab('schedules')" />
      </nav>
    </div>
    <div class="flex flex-row gap-8 px-12 pb-12">
      <aside v-if="activeTab === 'personal'" class="w-1/4 bg-white p-8 border border-gray-200 rounded-lg flex flex-col items-center">
        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Profile" class="w-28 h-28 rounded-full mb-6 object-cover shadow" />
        <div class="w-full">
          <div class="sidebar-info-block">
            <div class="sidebar-label">First Name</div>
            <div class="sidebar-value">John</div>
          </div>
          <div class="sidebar-info-block">
            <div class="sidebar-label">Last Name</div>
            <div class="sidebar-value">Doe</div>
          </div>
          <div class="sidebar-info-block">
            <div class="sidebar-label">Date of Birth</div>
            <div class="sidebar-value">September 21,2025</div>
          </div>
          <div class="sidebar-info-block">
            <div class="sidebar-label">Medication</div>
            <div class="sidebar-value">Tylenol</div>
          </div>
          <div class="sidebar-info-block">
            <div class="sidebar-label">Diagnosis</div>
            <div class="sidebar-value">Bipolar</div>
          </div>
          <div class="sidebar-info-block">
            <div class="sidebar-label">Allergies</div>
            <div class="sidebar-value">Seafood</div>
          </div>
        </div>
      </aside>
      <main class="flex-1">
        <section class="space-y-6">
          <template v-if="activeTab === 'personal'">
            <div class="border border-gray-200 rounded-lg p-6 bg-white">
              <div class="flex items-center gap-2 font-semibold mb-4 text-lg"><i class="pi pi-user"></i> Student</div>
              <div class="grid grid-cols-3 gap-4 text-sm">
                <div class="info-block-v2">
                  <div class="info-label-v2">Status</div>
                  <div class="info-value-v2">Active</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Class</div>
                  <div class="info-value-v2">Class 1</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Location</div>
                  <div class="info-value-v2">Location</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Father Name</div>
                  <div class="info-value-v2">Pending</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Mother Name</div>
                  <div class="info-value-v2">Class 3</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Mother Maiden Name</div>
                  <div class="info-value-v2">Location C</div>
                </div>
              </div>
            </div>
            <div class="border border-gray-200 rounded-lg p-6 bg-white">
              <div class="flex items-center gap-2 font-semibold mb-4 text-lg"><i class="pi pi-phone"></i> Contact</div>
              <div class="grid grid-cols-3 gap-4 text-sm">
                <div class="info-block-v2">
                  <div class="info-label-v2">Status</div>
                  <div class="info-value-v2">Active</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Class</div>
                  <div class="info-value-v2">Class 1</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Location</div>
                  <div class="info-value-v2">Location</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Father Name</div>
                  <div class="info-value-v2">Pending</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Mother Name</div>
                  <div class="info-value-v2">Class 3</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Mother Maiden Name</div>
                  <div class="info-value-v2">Location C</div>
                </div>
              </div>
            </div>
            <div class="border border-gray-200 rounded-lg p-6 bg-white">
              <div class="flex items-center gap-2 font-semibold mb-4 text-lg"><i class="pi pi-home"></i> Address</div>
              <div class="grid grid-cols-3 gap-4 text-sm">
                <div class="info-block-v2">
                  <div class="info-label-v2">Status</div>
                  <div class="info-value-v2">Active</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Class</div>
                  <div class="info-value-v2">Class 1</div>
                </div>
                <div class="info-block-v2">
                  <div class="info-label-v2">Location</div>
                  <div class="info-value-v2">Location</div>
                </div>
              </div>
            </div>
          </template>
          <template v-else-if="activeTab === 'services'">
            <div class="rounded-lg p-12 bg-white text-center text-gray-600">
              <i class="pi pi-lightbulb text-7xl text-gray-400 mb-4"></i>
              <div class="text-2xl font-semibold mb-2">No Services Available</div>
              <div class="mb-6">Start by adding a therapy type to see your services here.</div>
              <Button icon="pi pi-plus" label="Add Therapy Type" class="p-button-outlined" />
            </div>
          </template>
          <template v-else-if="activeTab === 'documents'">
            <div class="border border-gray-200 rounded-lg p-12 bg-white text-center text-gray-600">
              <i class="pi pi-folder text-5xl text-gray-400 mb-4"></i>
              <div class="text-2xl font-semibold mb-2">No Documents</div>
              <div class="mb-6">Upload your first document to manage files for this student.</div>
              <Button icon="pi pi-upload" label="Upload Document" class="p-button-outlined" />
            </div>
          </template>
          <template v-else-if="activeTab === 'notes'">
            <div class="border border-gray-200 rounded-lg p-12 bg-white text-center text-gray-600">
              <i class="pi pi-comments text-5xl text-gray-400 mb-4"></i>
              <div class="text-2xl font-semibold mb-2">No Notes Yet</div>
              <div class="mb-6">Add a note to keep track of updates and observations.</div>
              <Button icon="pi pi-plus" label="Add Note" class="p-button-outlined" />
            </div>
          </template>
          <template v-else-if="activeTab === 'staffs'">
            <div class="border border-gray-200 rounded-lg p-12 bg-white text-center text-gray-600">
              <i class="pi pi-users text-5xl text-gray-400 mb-4"></i>
              <div class="text-2xl font-semibold mb-2">No Staff Assigned</div>
              <div class="mb-6">Assign staff to collaborate with this student.</div>
              <Button icon="pi pi-user-plus" label="Assign Staff" class="p-button-outlined" />
            </div>
          </template>
          <template v-else-if="activeTab === 'schedules'">
            <div class="border border-gray-200 rounded-lg p-12 bg-white text-center text-gray-600">
              <i class="pi pi-calendar text-5xl text-gray-400 mb-4"></i>
              <div class="text-2xl font-semibold mb-2">No Schedules</div>
              <div class="mb-6">Create a schedule to see appointments and sessions here.</div>
              <Button icon="pi pi-plus" label="Create Schedule" class="p-button-outlined" />
            </div>
          </template>
        </section>
      </main>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';
import Button from 'primevue/button';
import 'primeicons/primeicons.css';

const props = defineProps({
  activeTab: { type: String, default: 'personal' },
});
const emit = defineEmits(['tab-change']);
const activeTab = ref(props.activeTab);

const tabTitles = {
  personal: 'Personal Information',
  services: 'Services Recommended',
  documents: 'Documents',
  notes: 'Notes',
  staffs: 'Staffs',
  schedules: 'Schedules',
};

watch(() => props.activeTab, (val) => {
  activeTab.value = val;
});

function changeTab(tab) {
  activeTab.value = tab;
  emit('tab-change', tab);
}
</script>

<style scoped>
.sidebar-info-block {
  padding: 0.5rem 0 0.75rem 0;
  border-bottom: 1px solid #e5e7eb;
  margin-bottom: 0.25rem;
}
.sidebar-info-block:last-child {
  border-bottom: none;
}
.sidebar-label {
  color: #6b7280;
  font-size: 1rem;
  font-weight: 500;
  margin-bottom: 0.25rem;
  text-align: left;
}
.sidebar-value {
  color: #374151;
  font-size: 1.08rem;
  margin-left: 1.5rem;
  margin-bottom: 0.1rem;
  margin-top: 0.5rem;
  font-weight: 400;
  text-align: left;
}
.tab-btn {
  border: none !important;
  border-bottom: 2px solid transparent !important;
  background: none !important;
  color: #6b7280 !important;
  font-weight: 500;
  margin-bottom: -2px;
}
.tab-active {
  color: #2563eb !important;
  border-bottom: 2px solid #2563eb !important;
  background: none !important;
}
.info-block-v2 {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 0.5rem;
}
.info-label-v2 {
  color: #6b7280;
  font-size: 0.95rem;
  font-weight: 500;
  margin-bottom: 0.15rem;
}
.info-value-v2 {
  color: #374151;
  font-size: 1.05rem;
  margin-left: 1.5rem;
  margin-bottom: 0.1rem;
  margin-top: 0.25rem;
  font-weight: 400;
  text-align: left;
}
.header-btn-edit {
  border-color: #60a5fa !important;
  color: #2563eb !important;
}
.header-btn-print {
  border-color: #d1d5db !important;
  color: #374151 !important;
}
.header-btn-delete {
  border-color: #fca5a5 !important;
  color: #dc2626 !important;
}
</style>