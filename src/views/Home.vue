<template>
  <div>
    <div style="background-color: lightblue;display: flex; align-items: center; justify-content: space-between; margin-bottom: 15px">
      <img src="https://oit.uta.edu/_images/_assets/oit-logo.png" alt="">
      <span style="font-weight: 700; color: white">Name: Chen Lu, Id: 91906</span>
    </div>
    <el-card :body-style="{padding: '0 20px'}">
      <!-- Ques1 -->
      <div class='ques1'>
        <!--  search for magnitude greater than 5.0 -->
        <span class="ques">Ques1: Search for and count all earthquakes that occurred with a magnitude greater than 5.0</span>
        <el-button type="primary" icon="el-icon-search" size="mini" style="margin-left: 15px">search</el-button>
      </div>
      <el-divider></el-divider>
      <!-- Ques2 -->
      <div class='ques2'>
        <span class="ques">Ques2: Search for 2.0 to 2.5, 2.5 to 3.0, etc magnitude quakes for a one week,a range of days or the whole 30 days</span>
        <div>
          <el-select v-model="magnitude" placeholder="select magnitude" size="small">
            <el-option v-for="item in magnitudeOptions" :key="item.value" :label="item.label" :value="item.value">
            </el-option>
          </el-select>
          <el-select style="margin-left: 15px" v-model="duration" placeholder="select duration" size="small">
            <el-option v-for="item in durationOptions" :key="item.value" :label="item.label" :value="item.value">
            </el-option>
          </el-select>
          <el-button type="primary" icon="el-icon-search" size="mini" style="margin-left: 15px">search</el-button>
        </div>
      </div>
      <el-divider></el-divider>
      <!-- Ques3 -->
      <div class='ques3'>
        <span class="ques">Ques3: Find earthquakes that were near (20 km, 50 km?) of a specified location</span>
        <div>
          <el-select v-model="location" placeholder="select location" size="small">
            <el-option v-for="item in locationOptions" :key="item.value" :label="item.label" :value="item.value">
            </el-option>
          </el-select>
          <el-select style="margin-left: 15px" v-model="distance" placeholder="select distance" size="small">
            <el-option v-for="item in distanceOptions" :key="item.value" :label="item.label" :value="item.value">
            </el-option>
          </el-select>
          <el-button type="primary" icon="el-icon-search" size="mini" style="margin-left: 15px">search</el-button>
        </div>
      </div>
      <el-divider></el-divider>
      <!-- Ques4 -->
      <div class='ques4'>
        <span class="ques">Ques4: Find clusters of earthquakes</span>
        <el-button type="primary" icon="el-icon-view" size="mini" style="margin-left: 15px">show graph</el-button>
      </div>
      <el-divider></el-divider>
      <!-- Ques5 -->
      <div class='ques5'>
        <span class="ques">Ques5: Do large (>4.0 mag) occur more often at night?</span>
        <el-button type="primary" icon="el-icon-view" size="mini" style="margin-left: 15px">show answer</el-button>
      </div>
      <el-divider></el-divider>
      <!-- show data table -->
      <el-table :data="tableData" border stripe style="width: 100%">
        <el-table-column prop="time" label="time"></el-table-column>
        <el-table-column prop="latitude" label="latitude"></el-table-column>
        <el-table-column prop="longitude" label="longitude"></el-table-column>
        <el-table-column prop="depth" label="depth"></el-table-column>
        <el-table-column prop="mag" label="mag"></el-table-column>
        <el-table-column prop="magType" label="magType"></el-table-column>
        <el-table-column prop="nst" label="nst"></el-table-column>
        <el-table-column prop="gap" label="gap"></el-table-column>
        <el-table-column prop="dmin" label="dmin"></el-table-column>
        <el-table-column prop="rms" label="rms"></el-table-column>
        <el-table-column prop="updated" label="updated"></el-table-column>
        <el-table-column prop="place" label="place"></el-table-column>
        <el-table-column prop="type" label="type"></el-table-column>
        <el-table-column prop="horizontalError" label="horizontalError"></el-table-column>
        <el-table-column prop="depthError" label="depthError"></el-table-column>
        <el-table-column prop="magError" label="magError"></el-table-column>
        <el-table-column prop="magNst" label="magNst"></el-table-column>
        <el-table-column prop="locationSource" label="locationSource"></el-table-column>
        <el-table-column prop="magSource" label="status"></el-table-column>
      </el-table>
    </el-card>
  </div>
</template>

<script>
export default {
  async created () {

  },
  data () {
    return {
      data: [], // table data
      magnitudeOptions: [
        {
          value: '2.0-2.5',
          label: '2.0-2.5'
        },
        {
          value: '2.5-3.0',
          label: '2.5-3.0'
        }
      ],
      durationOptions: [
        {
          value: 'a week',
          label: 'a week'
        },
        {
          value: 'a range of days',
          label: 'a range of days'
        },
        {
          value: 'the whole 30 days',
          label: 'the whole 30 days'
        }
      ],
      distanceOptions: [
        {
          value: '20',
          label: '20km'
        },
        {
          value: '50',
          label: '50km'
        }
      ],
      duration: '', // ques2's data
      magnitude: '' // ques2's data
    }
  }
}
</script>

<style>
.ques {
  color: red;
  font-weight: 700;
}
</style>
