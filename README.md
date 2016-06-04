> Gulp plugin allow modify file in .pipe

```javascript
const gulp = require('gulp')

gulp.task('js', () => {
    const modifyFile = require('gulp-modify-file')

    return gulp
    .src('app/**/*.js')
    .pipe(modifyFile((content, path, file) => {
        const start = '(function (){\n'
        const end = '\n})()'

        return `${start}${content}${end}`
    }))
    .pipe(gulp.dest('build'))
})
```