<template>
  <Demo>
    <h2>基础用法</h2>
    <nut-cell>
      <nut-indicator :size="3" :current="3">step1</nut-indicator>
    </nut-cell>
    <nut-cell>
      <nut-row>
        <nut-col :span="12">
          <nut-button size="small" type="primary">主要按钮</nut-button>
        </nut-col>
        <nut-col :span="12">
          <nut-indicator block align="right" :size="6" :current="5">step1</nut-indicator>
        </nut-col>
      </nut-row>
    </nut-cell>
    <h2>block用法</h2>
    <nut-cell>
      <nut-indicator block algin="center" :size="6" :current="5">step1</nut-indicator>
    </nut-cell>
    <nut-cell>
      <nut-indicator block align="left" :size="6" :current="1">step1</nut-indicator>
    </nut-cell>
    <nut-cell>
      <nut-indicator block align="right" :size="6" :current="5">step1</nut-indicator>
    </nut-cell>
    <h2>不补0</h2>
    <nut-cell>
      <nut-indicator :fill-zero="false" :size="6" :current="5">step1</nut-indicator>
    </nut-cell>
  </Demo>
</template>
