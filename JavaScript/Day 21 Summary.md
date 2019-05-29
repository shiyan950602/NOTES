# Day 21 Summary

1. Gulp 配置

   - 压缩并监听 JS SASS IMG 

   - ```javascript
     //引入所需插件
     
     const gulp = require('gulp'),
           uglify = require('gulp-uglify'),
           sass = require('gulp-sass'),
           rename = require('gulp-rename'),
           imagemin = require('gulp-imagemin'),
           concat = require('gulp-concat');
     
     //发布任务
     
     gulp.task('js',()=>{
         gulp.src('./src/js/*.js')
         .pipe(concat('all.js'))
         .pipe(uglify())
         .pipe(rename({'suffix' : '.min'}))
         .pipe(gulp.dest('./dist/js'));
     })
     gulp.task('sass',()=>{
         gulp.src('./src/sass/*.scss')
         .pipe(sass({outputStyle: 'expanded'}))
         .pipe(rename({'suffix' : '.min'}))
         .pipe(gulp.dest('./dist/css'));
     })
     gulp.task('image',()=>{
         gulp.src('./src/image/*.*')
         .pipe(imagemin())
         .pipe(gulp.dest('./dist/image'))
     })
     gulp.task('default',()=>{
         gulp.watch('./src/js/*.js',['js']);
         gulp.watch('./src/image/*.*',['img']);
         gulp.watch('./src/sass/*.scss',['sass']);
     })
     ```

     